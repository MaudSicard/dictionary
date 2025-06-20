# 🟦 Catégorie : Base en programmation

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
    mark {
      background: yellow;
      padding: 0;
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

<!-- Content in which to search -->
  <div id="content" markdown="1">

## ✅ API

Application Programming Interface - Interface logicielle permettant à deux applications de communiquer entre elles via des requêtes standardisées (HTTP, REST, etc.). Les API sont utilisées pour :

- Accéder à des services externes : Par exemple, récupérer des données météo ou afficher une carte interactive.
- Faciliter l’intégration : Permettre à plusieurs applications de fonctionner ensemble sans connaître les détails internes de chacune.
- Automatiser des tâches : Comme l’envoi de notifications ou la gestion de bases de données.

Il existe plusieurs types d’API :

- API REST (Representational State Transfer) : Basées sur des requêtes HTTP et des formats de réponse JSON ou XML.
-API SOAP (Simple Object Access Protocol) : Utilisant XML pour échanger des données de manière sécurisée.
- API GraphQL : Offrant plus de flexibilité en permettant aux clients de spécifier exactement les données dont ils ont besoin."
Architecture hexagonale Modèle architectural (aussi appelé "Ports and Adapters") visant à isoler la logique métier du reste de l’application (UI, base de données, etc.) grâce à des interfaces.

## ✅ API GraphQl

GraphQL est un **langage de requête** et un **environnement d'exécution** conçu pour optimiser la récupération des données via une API. Contrairement aux APIs REST traditionnelles, où chaque endpoint renvoie des données prédéfinies, GraphQL permet aux clients de **spécifier exactement** les données qu'ils souhaitent obtenir.

### **Fonctionnement d'une API GraphQL**

1. **Définition du schéma** : Un schéma GraphQL décrit les types de données disponibles et leurs relations. Il est défini avec un langage spécifique (`GraphQL Schema Language`).
2. **Résolveurs** : Ce sont des fonctions qui récupèrent les données associées à chaque champ d’un type de données. Ils permettent d'interroger une base de données ou d'autres sources.
3. **Requêtes et mutations** :
   - **Requêtes (`query`)** : Permettent de récupérer des données.
   - **Mutations (`mutation`)** : Permettent de modifier des données (ajout, mise à jour, suppression).
4. **Validation et exécution** : Avant d’exécuter une requête, l’API GraphQL valide la requête par rapport au schéma défini.

### **Exemple de requête GraphQL**

```graphql
query {
  utilisateur(id: ""123"") {
    nom
    email
    articles {
      titre
      contenu
    }
  }
}
```

Cette requête demande uniquement les champs `nom`, `email` et `articles` d'un utilisateur spécifique.

### **Avantages de GraphQL**

✅ **Flexibilité** : Les clients récupèrent uniquement les données nécessaires.
✅ **Moins de surcharge réseau** : Évite les requêtes multiples et les réponses volumineuses.
✅ **Évolution facile** : Ajout de nouveaux champs sans impacter les requêtes existantes.

## ✅ API REST

Une **API REST** (**Representational State Transfer**) est une interface qui permet aux applications de communiquer entre elles via le protocole **HTTP**. Elle repose sur plusieurs principes clés :

### **Principes fondamentaux**

1. **Architecture client-serveur** : Le client envoie des requêtes et le serveur répond avec des données.
2. **Stateless** : Chaque requête contient toutes les informations nécessaires, sans dépendre d'un état stocké côté serveur.
3. **Cache** : Les réponses peuvent être mises en cache pour améliorer les performances.
4. **Interface uniforme** : Les ressources sont identifiées par des **URI** et manipulées via des méthodes HTTP standard (`GET`, `POST`, `PUT`, `DELETE`).
5. **Système en couches** : Permet d'ajouter des intermédiaires (proxies, load balancers) sans impacter la communication.
6. **Code à la demande (optionnel)** : Le serveur peut envoyer du code exécutable au client.

### **Exemple de requête REST**

Une requête `GET` pour récupérer un utilisateur :

```http
GET /users/123 HTTP/1.1
Host: api.example.com
Accept: application/json
```

Réponse JSON :

```json
{
  ""id"": 123,
  ""name"": ""Alice"",
  ""email"": ""alice@example.com""
}
```

### **Avantages de REST**

✅ **Simplicité** : Basé sur HTTP, facile à implémenter.
✅ **Scalabilité** : Adapté aux architectures distribuées et aux microservices.
✅ **Interopérabilité** : Compatible avec de nombreux langages et plateformes.

## ✅ Asynchrone et Réactivité

L'**asynchronisme** et la **réactivité** sont deux concepts liés mais distincts en informatique et en programmation.

### 🔹 **Asynchronisme**

L'asynchronisme désigne un mode d'exécution où une tâche peut être lancée sans attendre la fin des précédentes. Cela permet d'éviter le **blocage** et d'améliorer la fluidité des opérations.
Exemple : Lorsqu'un programme effectue une requête réseau, il peut continuer à exécuter d'autres tâches pendant qu'il attend la réponse.

### 🔹 **Réactivité**

La réactivité concerne la capacité d'un système à **réagir rapidement** aux événements externes. Un système réactif est conçu pour répondre efficacement aux changements et aux sollicitations.
Exemple : Une interface utilisateur réactive met à jour instantanément l'affichage en fonction des actions de l'utilisateur.

### 🔹 **Différences clés**

| **Asynchronisme** | **Réactivité** |
|------------------|--------------|
| Exécution non bloquante | Réponse rapide aux événements |
| Permet le multitâche | Optimise l'expérience utilisateur |
| Utilisé dans les appels réseau, les tâches de fond | Utilisé dans les interfaces interactives, les systèmes temps réel |

## ✅ Authentification

Processus de vérification de l'identité d'un utilisateur ou d’un système avant de lui accorder un accès. Exemple : mot de passe, token, biométrie.

## ✅ Automatisation des tests

Utilisation d’outils et de scripts pour exécuter automatiquement des tests sur une application afin d’en vérifier la qualité à chaque changement.

## ✅ Boilerplate

Code standard souvent nécessaire mais répétitif, utilisé dans de nombreux projets (ex : configuration de base, code de démarrage).

## ✅ Cache

Mémoire temporaire utilisée pour stocker les données fréquemment utilisées afin de réduire le temps d’accès ou la charge sur le système.

## ✅ ERP

Enterprise Resource Planning - Système informatique permettant de gérer et d'automatiser les processus de gestion clés d'une entreprise au sein d'une plateforme intégrée.

## ✅ Faille XSS

Vulnérabilité de sécurité où un attaquant injecte du code JavaScript malveillant dans une page web vue par d'autres utilisateurs.

## ✅ File ou Queue

Structure de données (FIFO) utilisée pour stocker des messages ou tâches en attente de traitement par des consommateurs.

## ✅ Framework

Ensemble structuré d’outils, de bibliothèques et de conventions facilitant le développement d’applications (ex : Spring, Angular, Django).

## ✅ Injection SQL

Technique d’attaque consistant à insérer du SQL malveillant dans une requête afin de manipuler ou détourner une base de données.

## ✅ Library (Bibliothèque)

Ensemble de fonctions ou de classes réutilisables fournissant des fonctionnalités spécifiques, sans imposer de structure globale comme un framework.

## ✅ Memcache

Système de cache distribué en mémoire conçu pour accélérer les applications web en réduisant les accès aux bases de données.

## ✅ Message broker

Intermédiaire logiciel qui permet l’échange de messages entre différents systèmes ou services via des files ou des topics, facilitant l’asynchronisme et le découplage.

## ✅ Microservices

Style d’architecture logicielle où l’application est composée de petits services indépendants, chacun déployable et scalable individuellement.

## ✅ Multithreading

Technique permettant d’exécuter plusieurs fils d’exécution (threads) simultanément au sein d’un même processus pour améliorer la réactivité ou la performance.

## ✅ MVC (Model-View-Controller)

Modèle architectural qui sépare une application en trois couches : le modèle (données), la vue (interface utilisateur) et le contrôleur (logique).

## ✅ ORM (Object-Relational Mapping)

Technique qui permet de manipuler des bases de données à travers des objets de code (ex : JPA, Hibernate, Sequelize).

## ✅ Permission

Règle définissant les droits d’accès ou d’exécution d’un utilisateur ou d’un système sur une ressource donnée (fichier, service, API).

## ✅ Redis

Base de données clé-valeur en mémoire, extrêmement rapide, utilisée comme cache, broker de messages ou base temporaire.

## ✅ SDK

(Software Development Kit) Un kit de développement logiciel (SDK) est un ensemble d’outils, de bibliothèques, de documentation, d’exemples de code, et parfois d’environnements de développement, fournis par un éditeur pour permettre aux développeurs de créer des applications pour une plateforme spécifique.

## ✅ Service

Composant ou unité fonctionnelle qui exécute une tâche spécifique dans un système distribué. En microservices, chaque service est autonome et indépendant.

## ✅ TDD

(Test Driven Development) Méthodologie de développement où les tests sont écrits avant le code fonctionnel, forçant un design plus propre et testé en continu.

## ✅ Topic

Sujet ou canal de publication utilisé dans le modèle Pub/Sub pour diffuser des messages à plusieurs abonnés.

## ✅ Transaction

Ensemble d’opérations qui doivent être exécutées ensemble ou pas du tout, assurant la cohérence des données.

## ✅ Transaction ACID

Propriétés garantissant la fiabilité des transactions : Atomicité, Cohérence, Isolation, Durabilité (Durability).

## ✅ URI

Un **URI (Uniform Resource Identifier)** est une chaîne de caractères qui identifie une ressource sur un réseau, comme une page web, un fichier ou un service. Il est souvent confondu avec l'**URL (Uniform Resource Locator)**, qui est un type spécifique d'URI indiquant l'emplacement d'une ressource.

### **Structure d'un URI**

Un URI peut contenir plusieurs éléments :

- **Schéma** (`http`, `https`, `ftp`, `mailto`, etc.) : définit le protocole utilisé.
- **Autorité** (`example.com`) : identifie le domaine ou l'hôte.
- **Chemin** (`/page.html`) : indique l'emplacement de la ressource.
- **Requête** (`?id=123`) : contient des paramètres optionnels.
- **Fragment** (`#section1`) : pointe vers une partie spécifique de la ressource.

Exemple d'URI :

```
https://example.com/page.html?id=123#section1
```

Ici :

- `https` est le **schéma**.
- `example.com` est l'**autorité**.
- `/page.html` est le **chemin**.
- `id=123` est la **requête**.
- `section1` est le **fragment**.

### **Différence entre URI, URL et URN**

| **Terme** | **Définition** |
|-----------|---------------|
| **URI** | Identifie une ressource de manière unique. |
| **URL** | Spécifie l'emplacement d'une ressource et comment y accéder. |
| **URN** | Identifie une ressource par un nom unique, sans indiquer son emplacement. |

Par exemple :

- **URI** : `urn:isbn:0451450523` (identifiant d'un livre).
- **URL** : `https://example.com/book.pdf` (adresse d'un fichier).
- **URN** : `urn:ietf:rfc:2396` (nom unique d'une norme).

## ✅ Bearer Token

Un **Bearer Token** est un type de jeton d'accès utilisé dans le cadre de l'authentification **OAuth 2.0**. Il permet à un client d'accéder à des ressources protégées sans avoir à transmettre ses identifiants à chaque requête.

### 🔹 **Comment fonctionne un Bearer Token ?**

1. **Obtention du token** : Le client s'authentifie auprès d'un serveur d'autorisation (via un identifiant/mot de passe ou une clé API).
2. **Transmission du token** : Une fois obtenu, le token est inclus dans l'en-tête HTTP des requêtes :

   ```
   Authorization: Bearer <token>
   ```

3. **Validation du token** : Le serveur vérifie que le token est valide et autorise ou refuse l'accès à la ressource demandée.

### 🔹 **Sécurité et bonnes pratiques**

- **Expiration** : Les tokens ont une durée de vie limitée pour éviter les abus.
- **Stockage sécurisé** : Ne jamais exposer un token en clair dans une application.
- **Utilisation de HTTPS** : Toujours transmettre les tokens via une connexion sécurisée.
- **Révocation** : Les tokens compromis doivent pouvoir être invalidés.

Les Bearer Tokens sont largement utilisés pour sécuriser les **API REST**, les systèmes d'authentification unique (**SSO**) et les applications mobiles/web. Tu veux voir un exemple concret d'utilisation ? 🚀"
SSO "Le **Single Sign-On (SSO)** est une méthode d'authentification qui permet aux utilisateurs d'accéder à plusieurs applications ou services avec une seule authentification. Cela évite d'avoir à saisir plusieurs fois des identifiants et mots de passe.

### 🔹 **Comment fonctionne le SSO ?**

1. **Authentification initiale** : L'utilisateur se connecte une seule fois à un fournisseur d'identité (**IdP**).
2. **Transmission du jeton** : Une fois authentifié, un **jeton sécurisé** est généré et utilisé pour accéder aux autres services.
3. **Accès aux applications** : Les applications vérifient le jeton auprès du fournisseur d'identité et accordent l'accès sans demander de nouvelles authentifications.

### 🔹 **Avantages du SSO**

✅ **Gain de temps** : Plus besoin de saisir plusieurs mots de passe.
✅ **Sécurité renforcée** : Réduction des risques liés aux mots de passe faibles ou réutilisés.
✅ **Expérience utilisateur améliorée** : Connexion fluide et simplifiée.
✅ **Gestion centralisée** : Les administrateurs peuvent contrôler les accès plus efficacement.

### 🔹 **Exemples de technologies SSO**

- **OAuth 2.0** : Utilisé par Google, Facebook, etc.
- **SAML (Security Assertion Markup Language)** : Couramment utilisé en entreprise.
- **OpenID Connect** : Extension d'OAuth 2.0 pour l'authentification.

## ✅  Bson

**BSON** (**Binary JSON**) est un format de sérialisation binaire utilisé principalement par **MongoDB** pour stocker et échanger des données. Il est conçu pour être plus efficace que **JSON**, notamment en termes de rapidité de lecture et d'écriture.

### 🔹 **Caractéristiques de BSON**

- **Format binaire** : Contrairement à JSON, BSON encode les données sous forme binaire, ce qui accélère le traitement.
- **Support des types avancés** : BSON prend en charge des types non natifs à JSON, comme :
  - `Date` (stocké sous forme de timestamp)
  - `Binary Data` (pour les fichiers et objets binaires)
  - `ObjectId` (identifiant unique utilisé par MongoDB)
  - `Decimal128` (précision accrue pour les nombres décimaux)
- **Facilité de parcours** : BSON est optimisé pour être parcouru rapidement, ce qui est essentiel pour les bases de données.

### 🔹 **Différences entre BSON et JSON**

| **Caractéristique** | **JSON** | **BSON** |
|---------------------|---------|---------|
| **Format** | Texte | Binaire |
| **Lisibilité** | Facile (humain) | Difficile (machine) |
| **Efficacité** | Moins rapide | Plus rapide |
| **Types supportés** | Limité | Étendu (Date, ObjectId, etc.) |

### 🔹 **Exemple de document BSON**

Un document JSON :

```json
{
  ""name"": ""Alice"",
  ""age"": 30,
  ""createdAt"": ""2025-06-04T09:45:00Z""
}
```

Son équivalent en BSON (représentation binaire) :

```
\x16\x00\x00\x00  // Taille totale du document
\x02 name\x00\x06\x00\x00\x00Alice\x00  // Champ ""name""
\x10 age\x00\x1E\x00\x00\x00  // Champ ""age""
\x09 createdAt\x00\xE5\x07\x06\x04\x09\x45\x00\x00  // Champ ""createdAt"" (timestamp)
\x00  // Fin du document
```

### 🔹 **Utilisation de BSON avec MongoDB**

MongoDB stocke ses documents sous forme **BSON**, mais les convertit automatiquement en **JSON** lorsqu'on interroge la base. Tu peux manipuler BSON avec des bibliothèques comme **org.bson** en Java ou **bson** en Python.

## ✅ Bonnes pratiques de test

> Construire de **bons tests** dans une application **Quarkus** (ou toute autre application Java) repose sur plusieurs principes clés. Voici les bonnes pratiques pour des tests efficaces :

### 🔹 **1. Définir des objectifs clairs**

Avant d’écrire un test, demande-toi **ce que tu veux valider** :

- Test unitaire (vérifie une classe ou méthode isolée)
- Test d’intégration (valide l’interaction entre plusieurs composants)
- Test end-to-end (simule un cas d’utilisation complet)

---

### 🔹 **2. Utiliser des frameworks adaptés**

Quarkus propose des outils pour différents types de tests :
✅ **JUnit 5** : Tests unitaires classiques
✅ **Mockito** : Mocking de dépendances pour éviter les effets de bord
✅ **RestAssured** : Tests d’API REST
✅ **Testcontainers** : Simulation d’une base de données ou d’un service externe
✅ **Arquillian** : Tests d’intégration avancés

---

### 🔹 **3. Respecter la règle du ""Given-When-Then""**

Une bonne structure de test suit cette logique :

1. **Given** : Mise en place du contexte (`Préconditions`)
2. **When** : Exécution de l’action (`Action testée`)
3. **Then** : Vérification du résultat (`Assertions`)

Exemple avec JUnit et RestAssured :

```java
@QuarkusTest
public class ApiTest {

    @Test
    public void testGetUser() {
        // Given - Préparation du test
        String userId = ""123"";

        // When - Appel de l’API
        RestAssured.given()
            .when().get(""/users/"" + userId)
            .then().statusCode(200) // Then - Vérification du résultat
            .body(""id"", equalTo(userId));
    }
}
```

---

### 🔹 **4. Éviter les dépendances inutiles**

Chaque test doit être **isolé** et **indépendant** :
✅ Évite les interactions avec une vraie base de données (Mock ou Testcontainers)
✅ Ne fais pas dépendre un test d’un autre
✅ Nettoie les données après chaque test (`@BeforeEach` et `@AfterEach`)

Exemple avec **Testcontainers** pour une base de données isolée :

```java
static PostgreSQLContainer<?> postgres = new PostgreSQLContainer<>(""postgres:latest"");

@BeforeAll
static void startDatabase() {
    postgres.start();
}

@AfterAll
static void stopDatabase() {
    postgres.stop();
}
```

---

### 🔹 **5. Utiliser les annotations Quarkus pour l’injection de dépendances**

Quarkus permet de **mocker facilement les dépendances CDI** :

```java
@InjectMock
UserService userService;
```

Cela évite d’avoir à créer des objets manuellement.

---

### 🔹 **6. Tester les erreurs et cas limites**

Ne teste pas seulement les cas ""heureux"" :
✅ Vérifie les exceptions (`assertThrows`)
✅ Teste les cas aux limites (`null`, `valeurs extrêmes`, `permissions`)
✅ Vérifie les délais et performances

Exemple de test d’exception :

```java
assertThrows(IllegalArgumentException.class, () -> {
    new UserService().findUser(null);
});
```

---

### 🔹 **7. Automatiser l’exécution des tests**

Un bon test **doit être automatisé** pour éviter les erreurs humaines :
✅ Intégration avec **Maven** (`mvn test`)
✅ Ajout des tests dans **CI/CD** (GitHub Actions, GitLab CI, Jenkins)
✅ Génération de rapports de couverture avec **JaCoCo**

---

### 🔹 **Résumé**

✅ **Bien définir l’objectif du test**
✅ **Utiliser Given-When-Then pour structurer tes tests**
✅ **Isoler les tests et mocker les dépendances**
✅ **Tester les cas d’erreur et les limites**
✅ **Automatiser pour éviter les erreurs humaines**

## ✅ Changelog

 Un **changelog** (ou journal des modifications) est un document qui répertorie les évolutions d'un logiciel, d'une application ou d'un projet. Il permet de suivre les mises à jour, les corrections de bugs et les nouvelles fonctionnalités ajoutées à chaque version.

### 🔹 **Pourquoi utiliser un changelog ?**

✅ **Transparence** : Il informe les utilisateurs et développeurs des changements effectués.
✅ **Suivi des versions** : Il permet de comprendre les différences entre les versions successives.
✅ **Documentation** : Il sert de référence pour les équipes techniques et les utilisateurs.

### 🔹 **Structure d'un changelog**

Un changelog bien organisé inclut généralement :

- **Numéro de version** (ex. : v1.0.0, v1.2.3)
- **Date de publication**
- **Nouvelles fonctionnalités** (`Added`)
- **Modifications** (`Changed`)
- **Corrections de bugs** (`Fixed`)
- **Améliorations de performance**
- **Problèmes de sécurité résolus** (`Security`)

### 🔹 **Exemple de changelog**

```plaintext
# Changelog
## 1.2.0 - 2025-06-04
### Added
- Ajout d'une nouvelle API REST
### Fixed
- Correction d'un bug d'affichage sur mobile
### Security
- Mise à jour des dépendances pour corriger une faille de sécurité
```

## ✅ CQRS

Le **CQRS (Command Query Responsibility Segregation)** est un **modèle d'architecture** qui sépare les opérations de **lecture** et d'**écriture** dans un système. Cette séparation permet d'optimiser les performances, la scalabilité et la sécurité des applications.

### **Principes du CQRS**

- **Commandes** : utilisées pour **modifier** l'état du système (ajout, mise à jour, suppression).
- **Requêtes** : utilisées pour **lire** les données sans affecter l'état du système.
- **Modèles distincts** : les données peuvent être stockées différemment pour les lectures et les écritures afin d'améliorer l'efficacité.

### **Avantages du CQRS**

✅ **Optimisation des performances** : les lectures et écritures peuvent être **scalées indépendamment**.
✅ **Sécurité renforcée** : les accès en lecture et en écriture sont **clairement séparés**, réduisant les risques d'incohérence.
✅ **Flexibilité** : permet d'utiliser des **modèles de données adaptés** à chaque type d'opération.
✅ **Facilité d'intégration avec Event Sourcing** : les modifications peuvent être **stockées sous forme d'événements**, facilitant l'historisation des données.

### **Exemple d'implémentation**

Dans une application de gestion de commandes :

- Une **commande** `CreateOrderCommand` est envoyée pour créer une commande.
- Une **requête** `GetOrderQuery` est utilisée pour récupérer les détails d'une commande.

### **Cas d'utilisation**

- **Applications à forte charge** nécessitant une séparation des accès.
- **Systèmes distribués** où les lectures et écritures sont gérées indépendamment.
- **Applications nécessitant un historique détaillé** des modifications (ex. finance, logistique).

## ✅ Event Sourcing

L'**Event Sourcing** est un modèle architectural qui consiste à stocker **toutes les modifications** d'un système sous forme d'événements immuables, plutôt que de simplement enregistrer l'état actuel des données.

### **Principe de l'Event Sourcing**

- Chaque changement d'état est **capturé sous forme d'événement**.
- Ces événements sont **stockés chronologiquement** et peuvent être rejoués pour reconstruire l'état du système à n'importe quel moment.
- L'Event Sourcing garantit une **traçabilité complète** et facilite l'audit des données.

### **Exemple d'application**

Dans un système bancaire, au lieu de stocker uniquement le solde d'un compte, on enregistre chaque **dépôt et retrait** sous forme d'événement. Cela permet de **retracer l'historique complet** des transactions et d'assurer l'intégrité des données.

### **Avantages**

✅ **Traçabilité totale** : chaque modification est enregistrée et horodatée.
✅ **Audit et conformité** : idéal pour les systèmes nécessitant un suivi précis des actions.
✅ **Reconstruction d'état** : possibilité de rejouer les événements pour retrouver un état antérieur.
✅ **Scalabilité** : facilite la gestion des données distribuées et des microservices.

### **Cas d'utilisation**

- **Applications financières** : suivi des transactions bancaires.
- **Systèmes de gestion de commandes** : enregistrement des étapes d'une commande.
- **Applications collaboratives** : gestion des modifications et versioning.
- **Systèmes métier complexes** : analyse des décisions et optimisation des processus.

Système complexe et critique
Les **systèmes critiques** sont des systèmes dont la défaillance peut avoir des conséquences graves, comme des pertes humaines, des dommages matériels ou des impacts environnementaux. Ils sont souvent déployés dans des **environnements contraints** et doivent respecter des **normes strictes** pour garantir leur fiabilité et leur sécurité.

### 🔹 **Caractéristiques des systèmes critiques**

✅ **Tolérance aux pannes** : Ils doivent fonctionner même en cas de défaillance partielle.
✅ **Fiabilité élevée** : Chaque composant est conçu pour minimiser les risques d'erreur.
✅ **Sécurité renforcée** : Protection contre les cyberattaques et les erreurs humaines.
✅ **Normes strictes** : Certification selon des standards comme **DO-178C** (aviation), **ISO 26262** (automobile) ou **IEC 61508** (industrie).

### 🔹 **Exemples d'environnements contraints**

✅ **Aéronautique** : Systèmes de pilotage et de navigation (norme **DO-178C**).
✅ **Nucléaire** : Contrôle des réacteurs et gestion des radiations (**ISO 19443**).
✅ **Médical** : Appareils de diagnostic et de traitement (**IEC 60601**).
✅ **Automobile** : Systèmes embarqués et conduite autonome (**ISO 26262**).

### 🔹 **Méthodes de validation et de vérification**

✅ **Modélisation et simulation** : Vérification des comportements avant déploiement.
✅ **Tests en conditions extrêmes** : Évaluation sous stress thermique, électrique ou mécanique.
✅ **Analyse formelle** : Vérification mathématique des algorithmes critiques.
✅ **Redondance et sécurisation** : Multiplication des systèmes pour éviter les pannes.

## ✅ Logiciels embarqués

Les **logiciels embarqués** sont des programmes conçus pour fonctionner sur des systèmes dédiés, souvent avec des ressources limitées et des contraintes spécifiques. Voici un aperçu des **concepts de base et avancés** :

### 🔹 **Concepts de base**

✅ **Définition** : Un logiciel embarqué est un programme intégré à un matériel spécifique, conçu pour exécuter une tâche précise.
✅ **Temps réel** : Beaucoup de systèmes embarqués nécessitent un traitement immédiat des données (ex. : ABS, dispositifs médicaux).
✅ **Optimisation des ressources** : Contrairement aux ordinateurs classiques, les systèmes embarqués doivent fonctionner avec une mémoire et une puissance de calcul réduites.
✅ **Fiabilité et robustesse** : Ils doivent être hautement fiables, car ils sont souvent utilisés dans des environnements critiques (automobile, aéronautique, médical).

### 🔹 **Concepts avancés**

✅ **Systèmes d’exploitation embarqués** : Certains logiciels embarqués utilisent des OS spécialisés comme **FreeRTOS**, **VxWorks** ou **Linux embarqué**.
✅ **Communication et connectivité** : Intégration de protocoles comme **CAN**, **Modbus**, **MQTT** pour l’IoT.
✅ **Sécurité** : Protection contre les cyberattaques avec des techniques comme le chiffrement et l’authentification forte.
✅ **Optimisation énergétique** : Gestion efficace de la consommation pour les appareils autonomes (ex. : capteurs IoT, drones).

## ✅ IoT

L'**Internet des objets (IoT)** désigne un réseau d'appareils connectés qui échangent des données via Internet. Ces objets peuvent être des capteurs, des machines industrielles, des dispositifs médicaux ou des objets du quotidien comme des montres connectées ? Tout ce que vous devez ...](<https://kinsta.com/fr/base-de-connaissances/qu-est-ce-que-iot/>).

### 🔹 **Comment fonctionne l'IoT ?**

✅ **Capteurs et dispositifs** : Collectent des données (température, mouvement, pression…).
✅ **Connectivité** : Utilisent des technologies comme **Wi-Fi, Bluetooth, 5G, LoRaWAN** pour transmettre les données.
✅ **Traitement des données** : Les informations sont analysées via des plateformes cloud ou des systèmes embarqués.
✅ **Automatisation et action** : Les objets peuvent réagir en fonction des données reçues (ex. : thermostat intelligent qui ajuste la température).

### 🔹 **Exemples d'applications IoT**

✅ **Domotique** : Maisons intelligentes avec assistants vocaux et capteurs connectés.
✅ **Santé** : Montres et capteurs médicaux pour le suivi des patients.
✅ **Industrie 4.0** : Machines connectées pour optimiser la production.
✅ **Transport** : Voitures autonomes et gestion du trafic en temps réel.

### 🔹 **Défis et enjeux**

✅ **Sécurité** : Protection contre les cyberattaques et la gestion des données personnelles.
✅ **Interopérabilité** : Standardisation des protocoles pour une meilleure compatibilité entre appareils.
✅ **Impact environnemental** : Gestion de l'énergie et recyclage des composants électroniques.

## ✅ Système complexe

Un système complexe est un ensemble constitué d'un grand nombre d'entités en interaction dont l'intégration permet d'achever un but commun. Les systèmes complexes sont caractérisés par des propriétés émergentes qui n'existent qu'au niveau du système et ne peuvent pas être observées au niveau de ses constituants.

Dans certains cas, un observateur ne peut pas prévoir les rétroactions ou les comportements ou évolutions des systèmes complexes par le calcul, ce qui amène à les étudier à l'aide de la théorie du chaos.  Le seul moyen d'en connaître l'évolution du système est de faire l'expérience, éventuellement sur un modèle réduit. Lorsque l'on veut modéliser un système, on conçoit des règles d'évolution, puis l'on simule le système en itérant ces règles jusqu'à obtenir un résultat structuré. Un système est dit complexe si le résultat final n'est pas prédictible directement en connaissant les règles qui disent comment le système change. Étymologiquement, « compliqué » (du latin cum plicare, « plier ensemble ») signifie qu'il faut du temps et du talent pour comprendre l'objet d'étude, « complexe » (du latin cum plexus, « tissé ensemble ») signifie qu'il y a beaucoup d'intrications, que « tout est lié » ; que l'on ne peut étudier une petite partie du système de façon isolée et encore moins inférer l'ensemble à partir des composants. Les systèmes complexes sont généralement compliqués, mais le contraire n'est pas vrai i.e. que les systèmes compliqués ne sont pas généralement complexes[réf. nécessaire]. Les systèmes complexes sont définis, selon les cas et selon les auteurs, par leur structure, par l'existence d'interactions non linéaires, par l'émergence de niveaux d'organisation différents, ou par leurs comportements collectifs non triviaux (multistationnarité, chaos, bifurcations, auto-organisation, émergence, boucles de rétroaction).

## ✅ SMA

Les **systèmes multi-agents (SMA)** sont une approche informatique où plusieurs **agents autonomes** interagissent dans un environnement partagé pour résoudre des problèmes complexes. Ces agents peuvent être des logiciels, des robots ou des entités simulées.

### 🔹 **Principes des SMA**

✅ **Autonomie** : Chaque agent prend ses propres décisions sans contrôle centralisé.
✅ **Interaction** : Les agents communiquent et coopèrent pour atteindre un objectif commun.
✅ **Adaptabilité** : Le système évolue en fonction des conditions externes.
✅ **Distribution** : Les agents sont répartis sur plusieurs machines ou réseaux.

### 🔹 **Applications des SMA**

✅ **Intelligence artificielle** : Modélisation du comportement collectif (ex. : fourmis, essaims).
✅ **Simulation sociale** : Étude des interactions humaines et économiques.
✅ **Robotique** : Coordination de robots autonomes.
✅ **Finance** : Optimisation des marchés et des stratégies de trading.

### 🔹 **Exemple concret**

Dans un jeu vidéo simulant une ville, chaque personnage (agent) agit de manière autonome en fonction de son environnement et des interactions avec les autres personnages.

</div>
[⬅️ Retour à l'accueil](../index.md)
