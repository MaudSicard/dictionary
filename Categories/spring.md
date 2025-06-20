# 🟦 Catégorie : Spring

<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Search and Navigation Example</title>
  <!-- Include Mark.js from CDN -->
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

## ✅ Spring

Spring est l’un des frameworks Java les plus populaires pour le développement d’applications d’entreprise. Il est conçu pour simplifier la création d’applications robustes, évolutives et faciles à maintenir.  Spring repose sur plusieurs concepts clés :

Spring est l’un des frameworks Java les plus populaires pour le développement d’applications d’entreprise. Il est conçu pour simplifier la création d’applications robustes, évolutives et faciles à maintenir.  Spring repose sur plusieurs concepts clés :

- Injection de dépendances (DI - Dependency Injection) : Facilite la gestion des objets et leurs interactions.
- Programmation orientée aspect (AOP - Aspect-Oriented Programming) : Permet de séparer les préoccupations transversales (logging, sécurité, transactions).
- Configuration flexible : Spring peut être configuré via XML, annotations ou JavaConfig.
Intégration facile avec des bases de données et autres technologies : Compatible avec Hibernate, JPA, Kafka, RabbitMQ, etc.

### 🔥 Modules principaux de Spring

Spring est composé de plusieurs modules qui couvrent différents aspects du développement :

- Spring Core : Gestion des beans et injection de dépendances.

- Spring MVC : Développement d’applications web avec une architecture REST.

- Spring Boot : Simplifie le développement et le déploiement d’applications Spring.

- Spring Security : Gestion des authentifications et de la sécurité.

- Spring Data : Simplifie l’accès aux bases de données via JPA et JDBC.

- Spring Cloud : Optimisé pour les applications distribuées et microservices.

## ✅ @AliasFor

Permet de créer des alias dans les annotations personnalisées.

## ✅ @Aspect

Marque une classe comme aspect dans Spring AOP.

## ✅ @Autowired

Injecte automatiquement une dépendance par type. Peut être utilisé sur un constructeur, un champ ou une méthode.

## ✅ @Bean

Définit un bean manuellement dans une méthode annotée à l'intérieur d'une classe @Configuration.

## ✅ @Before, @After, @Around

Annotations AOP pour définir les points de coupe autour des méthodes ciblées.

## ✅ @Column

Spécifie une colonne spécifique de la table.

## ✅ @Component

Marque une classe comme un composant Spring à détecter automatiquement via le scanning.

## ✅ @ComponentScan

Active la détection automatique des composants dans le package spécifié.

## ✅ @ConditionalOnProperty

Active un bean si une certaine propriété est présente et a une valeur donnée.

## ✅ @Configuration

Indique qu'une classe contient des définitions de beans (équivalent Java de XML <beans>).

## ✅ @ConfigurationProperties

Permet de lier des propriétés externes (YAML/propriétés) à une classe Java.

## ✅ @Controller

Spécialisation de @Component pour définir un contrôleur dans une application Web MVC.

## ✅ @DataJpaTest

Configure uniquement la couche JPA pour les tests de repository.

## ✅ @DependsOn

Spécifie que le bean dépend d’un ou plusieurs autres beans.

## ✅ @EnableAspectJAutoProxy

Active le support de la programmation orientée aspect (AOP).

## ✅ @EnableAutoConfiguration

Active la configuration automatique basée sur les dépendances présentes.

## ✅ @EnableJpaRepositories

Active le support des repositories Spring Data JPA.

## ✅ @EnableWebSecurity

Active la configuration de sécurité Web personnalisée.

## ✅ @Entity

Marque une classe comme entité persistante (JPA/Hibernate).

## ✅ @EventListener

Marque une méthode comme écouteur d’un événement Spring.

## ✅ @GeneratedValue

Spécifie la stratégie de génération automatique de l’ID.

## ✅ @GetMapping, @PostMapping, @PutMapping, @DeleteMapping

Spécialisations de @RequestMapping pour des méthodes HTTP spécifiques.

## ✅ @Id

Indique l’identifiant unique de l'entité.

## ✅ @Import

Importe une ou plusieurs classes de configuration dans le contexte Spring.

## ✅ @Lazy

Diffère l’initialisation du bean jusqu’à son premier usage.

## ✅ @MockBean

Injecte un mock (Mockito) dans le contexte Spring.

## ✅ @ModelAttribute

Lien entre l’attribut du modèle et les paramètres d’une méthode.

## ✅ @PathVariable

Lie une variable de chemin d’URL à un paramètre de méthode.

## ✅ @PostAuthorize

Vérifie les autorisations après l'exécution d'une méthode.

## ✅ @PreAuthorize

Exécute une expression SpEL avant l'exécution d'une méthode (contrôle d'accès).

## ✅ @Primary

Indique le bean par défaut à injecter lorsqu’il y a plusieurs candidats.

## ✅ @Profile

Active un bean uniquement pour un profil spécifique (dev, prod, etc.).

## ✅ @Qualifier

Spécifie quel bean injecter lorsqu’il y a plusieurs candidats. Utilisé avec @Autowired.

## ✅ @Repository

L’annotation @Repository est en fait une spécialisation de @Component dans le contexte de Spring. Elle est conçue spécifiquement pour la couche DAO, c’est-à-dire les classes qui interagissent avec la base de données. En plus de permettre à Spring de détecter automatiquement ces classes via le component scanning, elle active aussi un mécanisme très utile : la traduction automatique des exceptions de persistance (comme celles de JPA ou JDBC) en exceptions Spring (DataAccessException et ses sous-classes).

Donc, pour résumer :

@Component → annotation générique pour tout bean Spring.

@Repository → version spécialisée pour les classes DAO, avec gestion automatique des exceptions de persistance.

## ✅ @RequestBody

Désérialise automatiquement le corps de la requête JSON/XML en un objet Java.

## ✅ @RequestMapping

Mappe une requête HTTP à une méthode de contrôleur. Peut être utilisé au niveau de la classe ou de la méthode.

## ✅ @RequestParam

Extrait une valeur de requête (query string ou formulaire) dans un paramètre.

## ✅ @ResponseBody

Indique que la valeur de retour doit être directement envoyée dans la réponse HTTP.

## ✅ @ResponseStatus

Définit le code HTTP à renvoyer pour une méthode ou une exception.

## ✅ @RestController

Combine @Controller + @ResponseBody, utilisé pour créer des API REST.

## ✅ @RolesAllowed

Alternative à @Secured, compatible avec JSR-250.

## ✅ @Scope

Définit le cycle de vie d’un bean : singleton, prototype, request, session, etc.

## ✅ @Secured

Restreint l’accès à une méthode à des rôles spécifiques.

## ✅ @Service

Spécialisation de @Component indiquant qu'une classe fournit une logique métier.

## ✅ @SpringBootApplication

Regroupe @Configuration, @EnableAutoConfiguration, et @ComponentScan. Point d’entrée principal.

## ✅ @SpringBootTest

Démarre le contexte complet de Spring pour les tests d’intégration.

## ✅ @Table

Spécifie la table correspondante dans la base de données.

## ✅ @TestConfiguration

Fournit des beans spécifiques aux tests.

## ✅ @Transactional

Indique que la méthode (ou classe) doit être exécutée dans une transaction.

## ✅ @Value

Injecte une valeur (propriété, constante, expression SpEL) dans un champ.

## ✅ @WebMvcTest

Lance uniquement le contexte Web MVC pour tester les contrôleurs.

## ✅ @WithMockUser

Utilisé dans les tests pour simuler un utilisateur authentifié.

</div>
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
