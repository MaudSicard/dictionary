# 🟦 Catégorie : Quarkus

<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Search and Navigation Example</title>
  <!-- Include Mark.js from CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"></script>
  <style>
    /* Container to center the search input */
    .search-container {
      display: flex;
      justify-content: center;
      margin: 20px 0;
    }
    /* Modern style for the search input */
    .search-input {
      width: 100%;
      max-width: 400px;
      padding: 12px 20px;
      font-size: 16px;
      border: 2px solid #e0e0e0;
      border-radius: 30px;
      transition: border-color 0.3s ease, box-shadow 0.3s ease;
      outline: none;
    }
    .search-input:hover {
      border-color: #9e9e9e;
    }
    .search-input:focus {
      border-color: #6200ea;
      box-shadow: 0 0 10px rgba(98, 0, 234, 0.3);
    }
    /* Styles for navigation buttons */
    .nav-buttons {
      text-align: center;
      margin: 20px 0;
    }
    .nav-buttons button {
      margin: 0 10px;
      padding: 8px 16px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.3s ease;
      border: 1px solid #ccc;
      border-radius: 4px;
      background: #f5f5f5;
    }
    .nav-buttons button:hover {
      background: #e0e0e0;
    }
    /* Style for highlighted marks */
    /* Container to center the search input */
    .search-container {
      display: flex;
      justify-content: center;
      margin: 20px 0;
    }
    /* Modern style for the search input */
    .search-input {
      width: 100%;
      max-width: 400px;
      padding: 12px 20px;
      font-size: 16px;
      border: 2px solid #e0e0e0;
      border-radius: 30px;
      transition: border-color 0.3s ease, box-shadow 0.3s ease;
      outline: none;
    }
    .search-input:hover {
      border-color: #9e9e9e;
    }
    .search-input:focus {
      border-color: #6200ea;
      box-shadow: 0 0 10px rgba(98, 0, 234, 0.3);
    }
    /* Styles for navigation buttons */
    .nav-buttons {
      text-align: center;
      margin: 20px 0;
    }
    .nav-buttons button {
      margin: 0 10px;
      padding: 8px 16px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.3s ease;
      border: 1px solid #ccc;
      border-radius: 4px;
      background: #f5f5f5;
    }
    .nav-buttons button:hover {
      background: #e0e0e0;
    }
    /* Style for highlighted marks */
    mark {
      background: yellow;
      padding: 0;
    }
    /* Style for the currently selected mark element */
    mark.current {
      background: orange;
      color: white;
    }
    /* Style for the currently selected mark element */
    mark.current {
      background: orange;
      color: white;
    }
  </style>
</head>
<body>
  <!-- Search input container -->
  <div class="search-container">
    <input type="text" id="search" class="search-input" placeholder="Search in the page...">
  </div>

  <!-- Navigation buttons for previous and next occurrences -->
  <div class="nav-buttons">
    <button id="prevBtn">Previous</button>
    <button id="nextBtn">Next</button>
    </div>

<!-- Content in which to search -->
<div id="content" markdown="1">

## ✅ JWT et Quarkus

Voici quelques détails supplémentaires pour bien gérer les **JWT** avec **Quarkus** :

### 🔹 **1. Générer et Vérifier un JWT**

Un **JSON Web Token (JWT)** est un jeton signé contenant des informations d’authentification. Il est composé de trois parties :

1. **Header** : Indique l’algorithme de signature (`RS256`, `HS256`, etc.).
2. **Payload** : Contient les **claims** (rôles, identifiant utilisateur…).
3. **Signature** : Garantit l'intégrité du jeton.

#### 📌 **Création d'un JWT en Java**

Tu peux utiliser **`io.smallrye.jwt.build.Jwt`** pour générer un token :

```java
import io.smallrye.jwt.build.Jwt;
import java.time.Instant;
import java.util.Set;

public class JwtGenerator {
    public static void main(String[] args) {
        String jwt = Jwt.issuer(""https://ton-issuer.com"")
                .subject(""user123"")
                .expiresAt(Instant.now().plusSeconds(3600))
                .groups(Set.of(""admin"", ""user""))
                .sign();

        System.out.println(""JWT généré : "" + jwt);
    }
}
```

Ce jeton expirera après **1 heure** et inclut les rôles `admin` et `user`.

---

### 🔹 **2. Vérification automatique avec Quarkus**

Avec Quarkus, il suffit de configurer **SmallRye JWT** pour que les tokens soient vérifiés automatiquement !

#### 📌 **Ajout de la configuration dans `application.properties`**

```properties
mp.jwt.verify.publickey.location=/chemin/vers/publicKey.pem
mp.jwt.verify.issuer=https://ton-issuer.com
quarkus.smallrye-jwt.enabled=true
```

#### 📌 **Protection des endpoints avec `@RolesAllowed`**

Une fois activé, tu peux sécuriser ton API en fonction des rôles du JWT :

```java
import jakarta.annotation.security.RolesAllowed;
import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;

@Path(""/admin"")
public class AdminResource {

    @GET
    @RolesAllowed(""admin"") // Seuls les utilisateurs avec le rôle ""admin"" peuvent accéder
    public String getAdminData() {
        return ""Données sécurisées pour Admins"";
    }
}
```

---

### 🔹 **3. Validation manuelle du JWT**

Si tu veux **valider manuellement** un JWT, tu peux utiliser **SmallRye JWT Parser** :

```java
import io.smallrye.jwt.auth.principal.JWTParser;
import io.smallrye.jwt.auth.principal.JsonWebToken;
import jakarta.enterprise.context.RequestScoped;
import jakarta.inject.Inject;

@RequestScoped
public class JwtService {

    @Inject
    JWTParser jwtParser;

    public boolean validateToken(String token) {
        try {
            JsonWebToken jwt = jwtParser.parse(token);
            return jwt.getIssuer().equals(""https://ton-issuer.com"");
        } catch (Exception e) {
            return false;
        }
    }
}
```

---

### 🛠 **Résumé et prochaines étapes**

✅ **Générer un JWT** avec `Jwt.issuer(...)`
✅ **Le valider automatiquement** grâce à Quarkus et `@RolesAllowed`
✅ **Faire une vérification manuelle** avec `JWTParser`

## ✅ Mutiny

Mutiny est une **bibliothèque de programmation réactive** conçue pour simplifier la gestion des opérations asynchrones en Java. Elle est utilisée principalement dans **Quarkus** pour gérer les flux de données et les événements de manière fluide.

### **Principes de Mutiny**

Mutiny repose sur un modèle **événementiel et réactif**, où les opérations sont déclenchées par des événements plutôt que par des appels bloquants. Elle propose deux types principaux :

- **`Uni<T>`** : Émet **un seul élément** ou une erreur. Idéal pour les opérations asynchrones comme les requêtes HTTP ou les accès à une base de données.
- **`Multi<T>`** : Émet **plusieurs éléments** sur une période donnée. Utile pour les flux de données continus, comme la lecture d’un fichier ou la réception de messages.

### **Exemple d'utilisation**

```java
import io.smallrye.mutiny.Uni;

public class MutinyExample {
    public Uni<String> fetchData() {
        return Uni.createFrom().item(""Données récupérées"")
                   .onItem().delayIt().by(Duration.ofSeconds(2));
    }
}
```

Ici, la méthode retourne un `Uni<String>` qui émet une valeur après **2 secondes**.

### **Pourquoi Mutiny ?**

Mutiny se distingue des autres bibliothèques réactives par :

- **Une API intuitive** : Facile à lire et à comprendre, sans nécessiter une expertise avancée en programmation fonctionnelle.
- **Une navigation simplifiée** : Contrairement à d'autres bibliothèques avec des centaines de méthodes, Mutiny propose une approche plus guidée.
- **Une intégration native avec Quarkus** : Elle est optimisée pour les applications réactives développées avec Quarkus.

### **Cas d'utilisation**

Mutiny est utilisée pour :

- **Les microservices réactifs** (REST, Kafka, WebSockets).
- **Les traitements de données en streaming**.
- **Les interactions avec des bases de données réactives**.

## ✅ @All

Injecte toutes les instances d’un type donné dans une liste.

## ✅ @ApplicationScoped

Portée du bean : une instance unique pour toute l’application.

## ✅ @Dependent

Portée par défaut, une nouvelle instance à chaque injection.

## ✅ @Disposes

Méthode appelée pour nettoyer un bean produit.

## ✅ @Inject

Injection de dépendance automatique.

## ✅ @Named

Attribue un nom à un bean pour l’injection par nom.

## ✅ @Produces

Définit un producteur de beans pour l’injection.

## ✅ @Qualifier

Crée un qualificateur personnalisé pour différencier les beans.

## ✅ @Singleton

Portée singleton, équivalente à @ApplicationScoped.

## ✅ @Path

Définit le chemin d’un endpoint REST.

## ✅ @GET, @POST, @PUT, @DELETE, @PATCH

Mappent les méthodes HTTP correspondantes.

## ✅ @Produces

Spécifie le type MIME de la réponse (ex. application/json).

## ✅ @Consumes

Spécifie le type MIME attendu dans la requête.

## ✅ @PathParam

Injection d’un paramètre de chemin.

## ✅ @QueryParam

Injection d’un paramètre de requête.

## ✅ @HeaderParam

Injection d’un en-tête HTTP.

## ✅ @FormParam

Injection d’un paramètre de formulaire.

## ✅ @QuarkusMain

Définit la classe principale pour une application CLI.

## ✅ @ConfigProperty (Injection)

Injection de propriétés de configuration.

## ✅ @RegisterForReflection

Enregistre une classe pour la réflexion, utile en mode natif.

## ✅ @Transactional

Gère les transactions automatiquement.

## ✅ @RolesAllowed

Spécifie les rôles autorisés pour accéder à une méthode ou une classe.

## ✅ @PermitAll

Permet l’accès à tous, sans restriction.

## ✅ @DenyAll

Interdit l’accès à tous.

## ✅ @ConfigProperty

Injection de propriétés de configuration.

## ✅ @Gauge, @Counted, @Timed

 Métriques pour le monitoring.

## ✅ @Health, @Liveness, @Readiness

 Indiquent l’état de santé de l’application.

## ✅ @QuarkusTest

Indique une classe de test utilisant Quarkus.


Indique une classe de test utilisant Quarkus.

## ✅ @TestHTTPEndpoint

Spécifie l’endpoint REST à tester.


Spécifie l’endpoint REST à tester.

## ✅ @TestHTTPResource

Injection d’une ressource HTTP pour les tests.


Injection d’une ressource HTTP pour les tests.

## ✅ @RestClient

Injection d’un client REST typé.


Injection d’un client REST typé.

## ✅ @Blocking

Indique qu’une méthode est bloquante.


Indique qu’une méthode est bloquante.

## ✅ @NonBlocking

Indique qu’une méthode est non bloquante.


Indique qu’une méthode est non bloquante.

## ✅ @Scheduled

Planifie l’exécution périodique d’une méthode.

Planifie l’exécution périodique d’une méthode.

</div>

[⬅️ Retour à l'accueil](../index.md)

 <script>
    // Get the search input and navigation buttons
    const searchInput = document.getElementById("search");
    const prevBtn = document.getElementById("prevBtn");
    const nextBtn = document.getElementById("nextBtn");
    // Define the context where Mark.js will search
    const context = document.querySelector("#content");
    const markInstance = new Mark(context);
    // Array to store marked elements and an index for the current result
    let markedElements = [];
    let currentIndex = -1;
    // Function to perform the marking based on the input keyword
    function doMark() {
      const keyword = searchInput.value.trim();
      // Remove previous markings
      markInstance.unmark({
        done: function() {
          if (keyword) {
            // Mark all occurrences of the keyword
            markInstance.mark(keyword, {
              done: function() {
                // Retrieve all generated <mark> elements
                markedElements = document.querySelectorAll("mark");
                // Reset current index (set to first element if available)
                currentIndex = markedElements.length > 0 ? 0 : -1;
                highlightCurrent();
              }
            });
          } else {
            // Clear marked elements and reset index if input is empty
            markedElements = [];
            currentIndex = -1;
          }
        }
      });
    }
    // Function to highlight the current marked element and scroll it into view
    function highlightCurrent() {
      // Remove the "current" class from all marked elements
      markedElements.forEach(el => el.classList.remove("current"));
      if (markedElements.length > 0 && currentIndex >= 0) {
        const currentMark = markedElements[currentIndex];
        currentMark.classList.add("current");
        // Scroll the current marked element smoothly into view, centered in the viewport
        currentMark.scrollIntoView({ behavior: "smooth", block: "center" });
      }
    }
    // Listen for input events to perform live search and marking
    searchInput.addEventListener("input", function() {
      doMark();
    });
    // Event listener for the "Previous" button to move to the previous occurrence
    prevBtn.addEventListener("click", function() {
      if (markedElements.length === 0) return;
      currentIndex = (currentIndex - 1 + markedElements.length) % markedElements.length;
      highlightCurrent();
    });
    // Event listener for the "Next" button to move to the next occurrence
    nextBtn.addEventListener("click", function() {
      if (markedElements.length === 0) return;
      currentIndex = (currentIndex + 1) % markedElements.length;
      highlightCurrent();
    });
  </script>
</body>
</html>