# 🟦 Catégorie : Quarkus


## ✅ JWT et Quarkus
> Voici quelques détails supplémentaires pour bien gérer les **JWT** avec **Quarkus** :

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

## ✅ @All
> Injecte toutes les instances d’un type donné dans une liste.
## ✅ @ApplicationScoped
> Portée du bean : une instance unique pour toute l’application.
## ✅ @Dependent
> Portée par défaut, une nouvelle instance à chaque injection.
## ✅ @Disposes
> Méthode appelée pour nettoyer un bean produit.
## ✅ @Inject
> Injection de dépendance automatique.
## ✅ @Named
> Attribue un nom à un bean pour l’injection par nom.
## ✅ @Produces
> Définit un producteur de beans pour l’injection.
## ✅ @Qualifier
> Crée un qualificateur personnalisé pour différencier les beans.
## ✅ @Singleton
> Portée singleton, équivalente à @ApplicationScoped.
## ✅ @Path
> Définit le chemin d’un endpoint REST.
## ✅ @GET, @POST, @PUT, @DELETE, @PATCH
> Mappent les méthodes HTTP correspondantes.
## ✅ @Produces
> Spécifie le type MIME de la réponse (ex. application/json).
## ✅ @Consumes
> Spécifie le type MIME attendu dans la requête.
## ✅ @PathParam
> Injection d’un paramètre de chemin.
## ✅ @QueryParam
> Injection d’un paramètre de requête.
## ✅ @HeaderParam
> Injection d’un en-tête HTTP.
## ✅ @FormParam
> Injection d’un paramètre de formulaire.
## ✅ @QuarkusMain
> Définit la classe principale pour une application CLI.
## ✅ @ConfigProperty
> Injection de propriétés de configuration.
## ✅ @RegisterForReflection
> Enregistre une classe pour la réflexion, utile en mode natif.
## ✅ @Transactional
> Gère les transactions automatiquement.
## ✅ @RolesAllowed
> Spécifie les rôles autorisés pour accéder à une méthode ou une classe.
## ✅ @PermitAll
> Permet l’accès à tous, sans restriction.
## ✅ @DenyAll
> Interdit l’accès à tous.
## ✅ @ConfigProperty
> Injection de propriétés de configuration.
## ✅ @Gauge, @Counted, @Timed
> Métriques pour le monitoring.
## ✅ @Health, @Liveness, @Readiness
> Indiquent l’état de santé de l’application.
## ✅ @QuarkusTest
> Indique une classe de test utilisant Quarkus.
## ✅ @TestHTTPEndpoint
> Spécifie l’endpoint REST à tester.
## ✅ @TestHTTPResource
> Injection d’une ressource HTTP pour les tests.
## ✅ @RestClient
> Injection d’un client REST typé.
## ✅ @Blocking
> Indique qu’une méthode est bloquante.
## ✅ @NonBlocking
> Indique qu’une méthode est non bloquante.
## ✅ @Scheduled
> Planifie l’exécution périodique d’une méthode.


[⬅️ Retour à l'accueil](../index.md)