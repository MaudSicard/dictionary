# 🟦 Catégorie : Spring


## ✅ Spring
> Spring est l’un des frameworks Java les plus populaires pour le développement d’applications d’entreprise. Il est conçu pour simplifier la création d’applications robustes, évolutives et faciles à maintenir.  Spring repose sur plusieurs concepts clés :
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
> Permet de créer des alias dans les annotations personnalisées.
## ✅ @Aspect
> Marque une classe comme aspect dans Spring AOP.
## ✅ @Autowired
> Injecte automatiquement une dépendance par type. Peut être utilisé sur un constructeur, un champ ou une méthode.
## ✅ @Bean
> Définit un bean manuellement dans une méthode annotée à l'intérieur d'une classe @Configuration.
## ✅ @Before, @After, @Around
> Annotations AOP pour définir les points de coupe autour des méthodes ciblées.
## ✅ @Column
> Spécifie une colonne spécifique de la table.
## ✅ @Component
> Marque une classe comme un composant Spring à détecter automatiquement via le scanning.
## ✅ @ComponentScan
> Active la détection automatique des composants dans le package spécifié.
## ✅ @ConditionalOnProperty
> Active un bean si une certaine propriété est présente et a une valeur donnée.
## ✅ @Configuration
> Indique qu'une classe contient des définitions de beans (équivalent Java de XML <beans>).
## ✅ @ConfigurationProperties
> Permet de lier des propriétés externes (YAML/propriétés) à une classe Java.
## ✅ @Controller
> Spécialisation de @Component pour définir un contrôleur dans une application Web MVC.
## ✅ @DataJpaTest
> Configure uniquement la couche JPA pour les tests de repository.
## ✅ @DependsOn
> Spécifie que le bean dépend d’un ou plusieurs autres beans.
## ✅ @EnableAspectJAutoProxy
> Active le support de la programmation orientée aspect (AOP).
## ✅ @EnableAutoConfiguration
> Active la configuration automatique basée sur les dépendances présentes.
## ✅ @EnableJpaRepositories
> Active le support des repositories Spring Data JPA.
## ✅ @EnableWebSecurity
> Active la configuration de sécurité Web personnalisée.
## ✅ @Entity
>Marque une classe comme entité persistante (JPA/Hibernate).
## ✅ @EventListener
> Marque une méthode comme écouteur d’un événement Spring.
## ✅ @GeneratedValue
> Spécifie la stratégie de génération automatique de l’ID.
## ✅ @GetMapping, @PostMapping, @PutMapping, @DeleteMapping
> Spécialisations de @RequestMapping pour des méthodes HTTP spécifiques.
## ✅ @Id
> Indique l’identifiant unique de l'entité.
## ✅ @Import
> Importe une ou plusieurs classes de configuration dans le contexte Spring.
## ✅ @Lazy
> Diffère l’initialisation du bean jusqu’à son premier usage.
## ✅ @MockBean
> Injecte un mock (Mockito) dans le contexte Spring.
## ✅ @ModelAttribute
> Lien entre l’attribut du modèle et les paramètres d’une méthode.
## ✅ @PathVariable
> Lie une variable de chemin d’URL à un paramètre de méthode.
## ✅ @PostAuthorize
> Vérifie les autorisations après l'exécution d'une méthode.
## ✅ @PreAuthorize
> Exécute une expression SpEL avant l'exécution d'une méthode (contrôle d'accès).
## ✅ @Primary
> Indique le bean par défaut à injecter lorsqu’il y a plusieurs candidats.
## ✅ @Profile
> Active un bean uniquement pour un profil spécifique (dev, prod, etc.).
## ✅ @Qualifier
> Spécifie quel bean injecter lorsqu’il y a plusieurs candidats. Utilisé avec @Autowired.
## ✅ @Repository
> Spécialisation de @Component pour la couche DAO (accès aux données), avec gestion des exceptions.
## ✅ @Repository
> Fournit un mécanisme de persistance et transforme les exceptions JPA en exceptions Spring.
## ✅ @RequestBody
> Désérialise automatiquement le corps de la requête JSON/XML en un objet Java.
## ✅ @RequestMapping
> Mappe une requête HTTP à une méthode de contrôleur. Peut être utilisé au niveau de la classe ou de la méthode.
## ✅ @RequestParam
> Extrait une valeur de requête (query string ou formulaire) dans un paramètre.
## ✅ @ResponseBody
> Indique que la valeur de retour doit être directement envoyée dans la réponse HTTP.
## ✅ @ResponseStatus
> Définit le code HTTP à renvoyer pour une méthode ou une exception.
## ✅ @RestController
> Combine @Controller + @ResponseBody, utilisé pour créer des API REST.
## ✅ @RolesAllowed
> Alternative à @Secured, compatible avec JSR-250.
## ✅ @Scope
> Définit le cycle de vie d’un bean : singleton, prototype, request, session, etc.
## ✅ @Secured
> Restreint l’accès à une méthode à des rôles spécifiques.
## ✅ @Service
> Spécialisation de @Component indiquant qu'une classe fournit une logique métier.
## ✅ @SpringBootApplication
> Regroupe @Configuration, @EnableAutoConfiguration, et @ComponentScan. Point d’entrée principal.
## ✅ @SpringBootTest
> Démarre le contexte complet de Spring pour les tests d’intégration.
## ✅ @Table
> Spécifie la table correspondante dans la base de données.
## ✅ @TestConfiguration
> Fournit des beans spécifiques aux tests.
## ✅ @Transactional
> Indique que la méthode (ou classe) doit être exécutée dans une transaction.
## ✅ @Value
> Injecte une valeur (propriété, constante, expression SpEL) dans un champ.
## ✅ @WebMvcTest
> Lance uniquement le contexte Web MVC pour tester les contrôleurs.
## ✅ @WithMockUser
> Utilisé dans les tests pour simuler un utilisateur authentifié.


[⬅️ Retour à l'accueil](../index.md)