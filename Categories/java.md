# 🟦 Catégorie : Java


## ✅ API Stream
> L'**API Stream** en Java, introduite avec **Java 8**, permet de traiter des collections de manière **fonctionnelle** et **efficace**. Elle offre une approche déclarative pour manipuler des ensembles de données sans avoir à gérer explicitement les boucles et les itérations.

### 🔹 **Concepts de base**
- **Flux de données** : Un Stream est une séquence d'éléments provenant d'une source (liste, tableau, fichier…).
- **Opérations intermédiaires** : Transformations appliquées aux éléments (ex. `map()`, `filter()`).
- **Opérations terminales** : Actions finales qui produisent un résultat (ex. `collect()`, `forEach()`).

### 🔹 **Fonctionnement**
L'API Stream repose sur un **pipeline de traitement** :
1. **Création du Stream** : À partir d'une collection ou d'un tableau.
2. **Application d'opérations intermédiaires** : Filtrage, transformation, tri…
3. **Exécution d'une opération terminale** : Collecte des résultats ou affichage.

Exemple :
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList(""Alice"", ""Bob"", ""Charlie"", ""David"");

        List<String> filteredNames = names.stream()
                                          .filter(name -> name.startsWith(""C""))
                                          .collect(Collectors.toList());

        System.out.println(filteredNames); // [Charlie]
    }
}
```

### 🔹 **Concepts avancés**
- **Streams parallèles** : Permettent d'exécuter des opérations en parallèle (`parallelStream()`).
- **Réduction (`reduce()`)** : Combine les éléments pour produire une valeur unique.
- **Groupement (`groupingBy()`)** : Regroupe les éléments selon un critère.
- **FlatMap (`flatMap()`)** : Transforme un Stream de collections en un Stream d'éléments.

### 🔹 **Cas d'utilisation**
✅ **Traitement de grandes collections** sans boucle explicite
✅ **Optimisation des performances** grâce au traitement paresseux
✅ **Manipulation avancée des données** avec filtrage et transformation


## ✅ Applet
> Une applet est un programme Java qui s'exécute dans un logiciel de navigation supportant Java ou dans l'appletviewer du JDK.
## ✅ Artifact
> En Java, un **artifact** est un fichier produit lors de la compilation et du packaging d'un projet. Il peut s'agir d'une bibliothèque (JAR), d'une application (WAR, EAR) ou d'autres types de fichiers contenant du code ou des ressources.
> Les artifacts sont souvent gérés par des systèmes comme **Maven** ou **Gradle**, qui facilitent leur création et leur distribution. Par exemple, avec Maven, un artifact est défini par trois éléments clés :
- **Group ID** : identifie l'organisation ou le projet.
- **Artifact ID** : nom spécifique de l'artifact.
- **Version** : numéro de version.
> Dans le contexte du développement, un artifact est essentiel pour partager des modules de code entre différentes applications et équipes.

## ✅ Autoboxing
> L'autoboxing en Java est le processus automatique par lequel le compilateur convertit un type primitif (comme int, double, boolean) en son équivalent objet de classe enveloppe (Integer, Double, Boolean). L'opération inverse, appelée unboxing, consiste à convertir un objet de classe enveloppe en son type primitif correspondant. L'autoboxing et l'unboxing permettent d'utiliser les types primitifs et leurs classes enveloppes de manière interchangeable, facilitant l'utilisation des collections et des génériques en Java.
## ✅ Beans
> Les JavaBeans sont des composants réutilisables introduits par le JDK 1.1. De nombreuses fonctionnalités ont ensuite été ajoutées pour développer des caractéristiques de ces composants. Les beans sont prévus pour pouvoir interagir avec d'autres beans au point de pouvoir développer une application simplement en assemblant des beans avec un outil graphique dédié. Sun fournit gratuitement un tel outil : le B.D.K. (Bean Development Kit). Des composants réutilisables sont des objets autonomes qui doivent pouvoir être facilement assemblés entres eux pour créer un programme.

> Les JavaBeans possèdent plusieurs caractéristiques :
- la persistance : elle permet grâce au mécanisme de sérialisation de sauvegarder l'état d'un bean pour le restaurer. Ainsi si on assemble plusieurs beans pour former une application, on peut la sauvegarder.
la communication, grâce à des événements, qui utilise le modèle des écouteurs introduit par Java 1.1
- l'introspection : ce mécanisme permet de découvrir de façon dynamique l'ensemble des éléments qui composent le bean (attributs, méthodes et événements) sans avoir le code source.
- la possibilité de paramétrer le composant : les données du paramétrage sont conservées dans des propriétés."
## ✅ Collections
> Les collections en Java sont un ensemble de classes et d'interfaces qui permettent de stocker, manipuler et organiser des groupes d'objets. Elles font partie du framework Java Collections, qui offre des structures de données flexibles et optimisées pour diverses opérations comme la recherche, le tri, l'insertion et la suppression.
### 1. Les principales interfaces du framework Collections
Le framework Collections repose sur plusieurs interfaces essentielles :

List : Une collection ordonnée qui accepte les doublons (ex. ArrayList, LinkedList).

Set : Une collection qui ne permet pas les doublons (ex. HashSet, TreeSet).

Map : Une structure qui associe des clés à des valeurs (ex. HashMap, TreeMap).

Queue : Une structure de file d'attente (ex. PriorityQueue, LinkedList).

### 2. Exemples de classes du framework Collections
Voici quelques classes couramment utilisées :

ArrayList : Une liste dynamique qui permet un accès rapide aux éléments.

LinkedList : Une liste chaînée qui facilite l'insertion et la suppression.

HashSet : Un ensemble qui ne permet pas les doublons et offre une recherche rapide.

TreeSet : Un ensemble trié qui maintient les éléments dans un ordre naturel.

HashMap : Une table de hachage qui associe des clés uniques à des valeurs.

TreeMap : Une version triée de HashMap.

### 3. Méthodes courantes des collections
Les collections offrent plusieurs méthodes utiles :

add(E e): Ajoute un élément à la collection.

remove(Object o): Supprime un élément.

contains(Object o): Vérifie si un élément est présent.

size(): Retourne le nombre d'éléments.

clear(): Supprime tous les éléments.

iterator(): Permet de parcourir la collection.

## ✅ Collections - Exemples
> Ces cinq structures de données en Java sont utilisées pour stocker et manipuler des collections d'éléments, mais elles ont des caractéristiques différentes qui les rendent adaptées à divers cas d'utilisation. Voici un comparatif :

### 🔹 **Liste (List)**
Ces structures conservent l’ordre des éléments et permettent les doublons.
1. **ArrayList**
   - Stocke les éléments dans un tableau dynamique.
   - Accès rapide aux éléments via leur index (**O(1)** en moyenne).
   - Insertion/suppression lentes au milieu de la liste (**O(n)**).
   - Idéal pour les **opérations de lecture fréquentes**.

2. **LinkedList**
   - Implémentée sous forme de liste chaînée (chaque élément pointe vers le suivant/précédent).
   - Insertion/suppression rapides à n’importe quelle position (**O(1)**).
   - Accès aux éléments plus lent que `ArrayList` (**O(n)**).
   - Utile quand **les insertions et suppressions sont fréquentes**.

---

### 🔹 **Ensemble (Set)**
Ces structures **ne permettent pas les doublons** et sont optimisées pour la recherche.

3. **HashSet**
   - Basé sur une **table de hachage**.
   - Très rapide pour ajouter/rechercher un élément (**O(1)** en moyenne).
   - Ne garantit **pas l’ordre** des éléments.
   - À privilégier pour les **recherches rapides sans ordre particulier**.

4. **TreeSet**
   - Basé sur un **arbre binaire équilibré (Red-Black Tree)**.
   - Stocke les éléments **dans un ordre trié**.
   - Plus lent que `HashSet` pour ajouter/rechercher (**O(log n)**).
   - Utile quand **l’ordre naturel des éléments est important**.

---

### 🔹 **Map (Dictionnaire)**
Stocke des **paires clé-valeur**.

5. **HashMap**
   - Basé sur une table de hachage.
   - Recherche rapide via la clé (**O(1)** en moyenne).
   - Ne garantit **pas l’ordre** des clés.
   - Idéal pour **associer des clés uniques à des valeurs**.

👉 **En résumé** :
- **Lecture fréquente** → `ArrayList`
- **Insertions/suppressions fréquentes** → `LinkedList`
- **Stockage sans doublons rapide** → `HashSet`
- **Stockage trié** → `TreeSet`
- **Stockage clé-valeur** → `HashMap`

## ✅ Compilateur Javac
> Cet outil est le compilateur : il utilise un fichier source Java fourni en paramètre pour créer un ou plusieurs fichiers contenant le bytecode Java correspondant. Pour chaque fichier source, un fichier portant le même nom avec l'extension .class est créé si la compilation se déroule bien.
## ✅ Final
> Indique qu'une variable ne peut pas être réassignée après son initialisation. Il peut aussi être appliqué aux méthodes (empêchant la surcharge) et aux classes (empêchant l'héritage).
## ✅ Garbage collector
> Mécanisme automatique de gestion mémoire qui libère les objets non utilisés pour éviter les fuites mémoire.
## ✅ Generics
> Les génériques en Java permettent de créer des classes, interfaces et méthodes qui peuvent fonctionner avec différents types de données tout en garantissant la sécurité du typage à la compilation. Ils ont été introduits dans Java 5 pour éviter les erreurs de conversion de type et améliorer la lisibilité du code.
### 1. Pourquoi utiliser les génériques ?
- Sécurité du typage : Évite les erreurs de conversion (ClassCastException).
- Réutilisation du code : Permet d'écrire des classes et méthodes indépendantes du type de données.
- Lisibilité et maintenabilité : Rend le code plus clair et compréhensible.

### 2. Syntaxe des génériques
Les génériques utilisent des paramètres de type (<T>, <E>, <K, V>, etc.) pour définir des classes ou des méthodes génériques. Les génériques sont essentiels pour écrire du code réutilisable, sécurisé et maintenable en Java

## ✅ Hibernate
> Hibernate est une solution open source de type ORM (Object Relational Mapping) qui permet de faciliter le développement de la couche persistance d'une application. Hibernate permet donc de représenter une base de données en objets Java et vice versa. Hibernate facilite la persistence et la recherche de données dans une base de données en réalisant lui-même la création des objets et les traitements de remplissage de ceux-ci en accédant à la base de données. La quantité de code ainsi épargnée est très importante d'autant que ce code est généralement fastidieux et redondant. Hibernate est très populaire notamment à cause de ses bonnes performances et de son ouverture à de nombreuses bases de données. Les bases de données supportées sont les principales du marché : DB2, Oracle, MySQL, PostgreSQL, Sybase, SQL Server, Sap DB, Interbase, ...

## ✅ Immutabilité
> En Java, l'immutabilité est un concept clé qui garantit qu'un objet ne peut pas être modifié après sa création. Cela améliore la sécurité, la performance et la gestion de la concurrence.
> Exemples d'objets immuables en Java :
- String : Une fois créée, une chaîne de caractères ne peut pas être modifiée.
- Integer, BigDecimal, LocalDate : Ces classes sont conçues pour être immuables.

### Comment créer une classe immuable ?
- Déclarer la classe final pour empêcher l'héritage.
- Définir tous les champs comme private final pour éviter leur modification.
- Ne pas fournir de setters, seulement des getters.

### Utiliser des copies défensives pour les objets mutables.  Avantages de l'immutabilité :
- Sécurité : Évite les modifications accidentelles.
- Thread-safe : Aucun risque de corruption des données en environnement concurrent.
- Optimisation : Peut être mis en cache et réutilisé efficacement.

## ✅ Inrtrospection
> L’introspection désigne la capacité d'un programme à analyser dynamiquement les propriétés et les méthodes d’un objet à l’exécution. Java offre des mécanismes permettant de découvrir ces informations sans connaître à l’avance la structure exacte de la classe. Cas d'usage : ORM (Hibernate, JPA) : Les ORM utilisent l’introspection pour cartographier les Beans avec une base de données sans écrire de code spécifique pour chaque classe. ✔ API REST et JSON : Transformer dynamiquement des Beans en JSON/XML pour une communication inter-systèmes. ✔ Bibliothèques UI : Génération automatique d'interfaces à partir des Beans, permettant une adaptation sans code statique.

## ✅ Interopérabilité
> L’interopérabilité signifie que les composants (ici, les Beans) peuvent être utilisés sur différentes plateformes ou systèmes sans modification majeure.
Dans le contexte des Beans :
Un Java Bean sérialisé peut être envoyé sur un réseau et lu par un autre programme, même s'il tourne sur un autre système.
Les JSON/XML Beans sont souvent utilisés pour échanger des données entre une application Java et d’autres technologies (JavaScript, Python, etc.).
Spring Beans et REST API permettent d’exposer des objets sous forme de services web, accessibles par différentes applications.

## ✅ Interpréteur java/javaw
>Ces deux outils sont les interpréteurs de bytecode : ils lancent le JRE, chargent les classes nécessaires et exécutent la méthode main de la classe passée en paramètre. java ouvre une console pour recevoir les messages de l'application alors que javaw n'en ouvre pas.
## ✅ J2EE
> J2EE est l'acronyme de Java 2 Entreprise Edition. Cette édition est dédiée à la réalisation d'applications pour entreprises. J2EE est basé sur J2SE (Java 2 Standard Edition) qui contient les API de base de Java. Depuis sa version 5, J2EE est renommée Java EE (Enterprise Edition).
## ✅ jar
> JAR est le diminutif de Java ARchive. C'est un format de fichier qui permet de regrouper des fichiers contenant du bytecode Java (fichier .class) ou des données utilisées en tant que ressources (images, son, ...). Ce format est compatible avec le format ZIP : les fichiers contenus dans un jar sont compressés de façon indépendante du système d'exploitation.
## ✅  Javadoc
> Javadoc est un outil fourni avec le JDK pour permettre la génération d'une documentation technique à partir du code source. Cet outil génère une documentation au format HTML à partir du code source Java et des commentaires particuliers qu'il contient. Un exemple concret de l'utilisation de cet outil est la documentation du JDK qui est générée grâce à Javadoc.
## ✅ JDBC
> JDBC (Java Database Connectivity) est une API Java qui permet aux applications de se connecter à une base de données et d'exécuter des requêtes SQL. Elle offre une interface standardisée pour interagir avec différents systèmes de gestion de bases de données (SGBD) via des pilotes JDBC spécifiques1.
>JDBC fonctionne en utilisant des pilotes qui traduisent les appels Java en commandes compréhensibles par la base de données. Il existe plusieurs types de pilotes JDBC, allant des pilotes reliant JDBC à ODBC aux pilotes natifs qui communiquent directement avec la base de données."

## ✅ JDK
> Le JDK de Sun/Oracle fournit un ensemble d'outils qui permettent de réaliser des applications. Ces outils sont peu ergonomiques car ils s'utilisent en ligne de commandes mais, en contrepartie, ils peuvent toujours être utilisés.
## ✅ JPA
> API Java Persistence - L'utilisation pour la persistance d'un mapping O/R permet de proposer un niveau d'abstraction plus élevé que la simple utilisation de JDBC : ce mapping permet d'assurer la transformation d'objets  vers la base de données et vice versa que cela soit pour des lectures ou des mises à jour (création, modification ou suppression). L'API propose un langage d'interrogation similaire à SQL mais utilisant des objets plutôt que des entités relationnelles de la base de données. L'API Java Persistence repose sur des entités qui sont de simples POJOs annotés et sur un gestionnaire de ces entités (EntityManager) qui propose des fonctionnalités pour les manipuler (ajout, modification suppression, recherche). Ce gestionnaire est responsable de la gestion de l'état des entités et de leur persistance dans la base de données.
## ✅ JRE
> Le JRE (Java Runtime Environment) est un environnement d'exécution qui permet d'exécuter des programmes écrits en langage Java. Il comprend une machine virtuelle Java (JVM), des bibliothèques logicielles et un plugin permettant l'exécution des programmes Java depuis les navigateurs web. Le JRE est souvent installé sur les ordinateurs pour garantir la compatibilité des applications Java avec différents systèmes d'exploitation2.
## ✅ JVM
> La machine virtuelle Java ou JVM (Java Virtual Machine) est un environnement d'exécution pour applications Java.
>C'est un des éléments les plus importants de la plate-forme Java. Elle assure l'indépendance du matériel et du système d'exploitation lors de l'exécution des applications Java. Une application Java ne s'exécute pas directement dans le système d'exploitation mais dans une machine virtuelle qui s'exécute dans le système d'exploitation et propose une couche d'abstraction entre l'application Java et ce système.
La machine virtuelle permet notamment :
* l'interprétation du bytecode
* l'interaction avec le système d'exploitation
* la gestion de sa mémoire grâce au ramasse-miettes
Son mode de fonctionnement est relativement similaire à celui d'un ordinateur : elle exécute des instructions qui manipulent différentes zones de mémoire dédiées de la JVM.
Une application Java ne fait pas d'appel direct au système d'exploitation (sauf en cas d'utilisation de JNI) : elle n'utilise que les API qui sont pour une large part écrites en Java sauf quelques-unes qui sont natives. Ceci permet à Java de rendre les applications indépendantes de l'environnement d'exécution.
La machine virtuelle ne connaît pas le langage Java : elle ne connaît que le bytecode qui est issu de la compilation de codes sources écrits en Java.
Les spécifications de la machine virtuelle Java définissent :
* Les concepts du langage Java
* Le format des fichiers .class
* Les fonctionnalités de la JVM
* Le chargement des fichiers .class
* Le bytecode
* La gestion des threads et des accès concurrents
* ...
Les fonctionnalités de la JVM décrites dans les spécifications sont abstraites : elles décrivent les fonctionnalités requises mais ne fournissent aucune implémentation ou algorithme d'implémentation. L'implémentation est à la charge du fournisseur de la JVM. Il existe de nombreuses implémentations de JVM dont les plus connues sont celles de Sun Microsystems/Oracle (HotSpot), IBM (J9), BEA/Oracle (JRockit), Azul (Zing), ...
Le respect strict de ces spécifications par une implémentation de la JVM garantit la portabilité et la bonne exécution du bytecode.
Ces spécifications sont consultables à l'url : https://docs.oracle.com/javase/specs/

## ✅ Maven
> Maven est un outil de construction de projets (build) open source développé par la fondation Apache, initialement pour les besoins du projet Jakarta Turbine. Il permet de faciliter et d'automatiser certaines tâches de la gestion d'un projet Java.
## ✅ POJO
> Un POJO (Plain Old Java Object) est un objet Java simple qui ne dépend d'aucun framework spécifique. Il est utilisé pour représenter des données de manière indépendante, sans imposer de contraintes particulières comme l'implémentation d'interfaces ou l'héritage de classes spécifiques.
> L'idée derrière les POJO est de garder les objets Java aussi simples que possible, facilitant ainsi leur réutilisation et leur lisibilité dans un programme. Contrairement aux JavaBeans, qui doivent être sérialisables et suivre certaines conventions (comme avoir un constructeur sans argument et des méthodes getter/setter), un POJO est plus libre dans sa structure.
## ✅ Primitifs
> En Java, les types primitifs sont des types de données de base qui ne sont pas des objets. Ils sont utilisés pour stocker des valeurs simples et sont plus efficaces en termes de mémoire et de performance que les objets. Java définit huit types primitifs :
### 1. Types numériques entiers
- byte (8 bits) : valeurs de -128 à 127.
- short (16 bits) : valeurs de -32 768 à 32 767.
- int (32 bits) : valeurs de -2 147 483 648 à 2 147 483 647.
- long (64 bits) : valeurs de -9 223 372 036 854 775 808 à 9 223 372 036 854 775 807.

### 2. Types numériques à virgule flottante
- float (32 bits) : précision simple.
- double (64 bits) : précision double.

### 3. Type caractère
- char (16 bits) : stocke un seul caractère Unicode.

### 4. Type booléen
- boolean : peut être true ou false.

## ✅ Sérialisation
> La sérialisation en Java consiste à convertir un objet en un format pouvant être stocké ou transmis (ex. un fichier, un flux réseau, une base de données). Cela permet de conserver l’état d’un objet et de le restaurer plus tard.

## ✅ Programmation orientée aspect
> (AOP - Aspect-Oriented Programming) : Permet de séparer les préoccupations transversales (logging, sécurité, transactions).

## ✅ Static	static
> Indique qu'une variable ou une méthode appartient à la classe elle-même plutôt qu'à une instance spécifique. Cela signifie qu'il n'est pas nécessaire de créer un objet pour y accéder.
## ✅ Static Final
> Lorsque ces deux mots-clés sont combinés (static final), cela signifie que la variable est une constante de classe, accessible sans instanciation et dont la valeur ne peut pas être modifiée. Pourquoi utiliser static final ?
- Améliore la lisibilité du code en définissant des valeurs constantes.
- Optimise la gestion de la mémoire en évitant la duplication des valeurs.
- Facilite la maintenance en centralisant les constantes. L'utilisation de static final en Java est recommandée dans plusieurs cas où une valeur doit rester constante et être partagée entre toutes les instances d'une classe
## ✅ Thread
> La **gestion des threads** en Java est essentielle pour exécuter plusieurs tâches en parallèle et optimiser les performances des applications. Java propose plusieurs mécanismes pour créer et gérer des threads efficacement.

### 🔹 **Concepts de base**
- **Thread** : Un fil d'exécution indépendant au sein d'un programme.
- **Multithreading** : Permet d'exécuter plusieurs threads simultanément.
- **Synchronisation** : Assure que plusieurs threads accédant aux mêmes ressources ne causent pas d'incohérences.

### 🔹 **Cycle de vie d'un thread**
Un thread passe par plusieurs états :
1. **Nouveau** : Créé mais non démarré.
2. **Exécutable** : Prêt à être exécuté par le processeur.
3. **En attente** : Suspendu temporairement (`sleep()`, `wait()`).
4. **Terminé** : A fini son exécution.

### 🔹 **Création de threads**
Java offre deux principales méthodes pour créer un thread :
1. **Étendre la classe `Thread`** :
   ```java
   class MyThread extends Thread {
       public void run() {
           System.out.println(""Thread en cours d'exécution !"");
       }
   }

   public class Main {
       public static void main(String[] args) {
           MyThread thread = new MyThread();
           thread.start();
       }
   }
   ```
2. **Implémenter l'interface `Runnable`** :
   ```java
   class MyRunnable implements Runnable {
       public void run() {
           System.out.println(""Thread via Runnable !"");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Thread thread = new Thread(new MyRunnable());
           thread.start();
       }
   }
   ```

### 🔹 **Concepts avancés**
- **Synchronisation (`synchronized`)** : Empêche les accès concurrents à une ressource partagée.
- **ExecutorService** : Fournit un pool de threads pour une gestion efficace.
- **Future & Callable** : Permet de récupérer un résultat après l'exécution d'un thread.
- **Fork/Join Framework** : Optimise le traitement parallèle des tâches complexes.

### 🔹 **Cas d'utilisation**
✅ **Traitement parallèle** pour améliorer la réactivité
✅ **Gestion des tâches en arrière-plan** (ex. téléchargement, calculs)
✅ **Optimisation des performances** en exploitant plusieurs cœurs


## ✅ Mutiny
> Mutiny est une **bibliothèque de programmation réactive** conçue pour simplifier la gestion des opérations asynchrones en Java. Elle est utilisée principalement dans **Quarkus** pour gérer les flux de données et les événements de manière fluide.

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

## ✅ CQRS
> Le **CQRS (Command Query Responsibility Segregation)** est un **modèle d'architecture** qui sépare les opérations de **lecture** et d'**écriture** dans un système. Cette séparation permet d'optimiser les performances, la scalabilité et la sécurité des applications.

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
> L'**Event Sourcing** est un modèle architectural qui consiste à stocker **toutes les modifications** d'un système sous forme d'événements immuables, plutôt que de simplement enregistrer l'état actuel des données.

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

## ✅ JAX-RS
> JAX-RS est une API Java conçue pour développer des services web RESTful. Elle permet de gérer des requêtes HTTP et d'exposer des ressources via des annotations simples. Voici quelques points clés :

- **Méthodes HTTP** : JAX-RS prend en charge les méthodes **GET, POST, PUT, DELETE** pour interagir avec les ressources.
- **Annotations** :
  - `@Path(""""/resource"""")` : Définit l'URI de la ressource.
  - `@GET`, `@POST`, `@PUT`, `@DELETE` : Spécifie la méthode HTTP utilisée.
  - `@Produces(""""application/json"""")` : Indique le format de réponse.
  - `@Consumes(""""application/json"""")` : Définit le format des données reçues.

Exemple de requête GET avec JAX-RS :
```java
import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;
import jakarta.ws.rs.Produces;
import jakarta.ws.rs.core.MediaType;

@Path(""""/hello"""")
public class HelloResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String sayHello() {
        return """"Bonjour, JAX-RS !"""";
    }
}
```
Tu peux tester cette API avec un client HTTP comme **Postman** ou **Insomnia**. Besoin d'un exemple plus avancé ? 😊JAX-RS est une API Java conçue pour développer des services web RESTful. Elle permet de gérer des requêtes HTTP et d'exposer des ressources via des annotations simples. Voici quelques points clés :

- **Méthodes HTTP** : JAX-RS prend en charge les méthodes **GET, POST, PUT, DELETE** pour interagir avec les ressources.
- **Annotations** :
  - `@Path(""""/resource"""")` : Définit l'URI de la ressource.
  - `@GET`, `@POST`, `@PUT`, `@DELETE` : Spécifie la méthode HTTP utilisée.
  - `@Produces(""""application/json"""")` : Indique le format de réponse.
  - `@Consumes(""""application/json"""")` : Définit le format des données reçues.

Exemple de requête GET avec JAX-RS :
```java
import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;
import jakarta.ws.rs.Produces;
import jakarta.ws.rs.core.MediaType;

@Path(""""/hello"""")
public class HelloResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String sayHello() {
        return """"Bonjour, JAX-RS !"""";
    }
}
```
Tu peux tester cette API avec un client HTTP comme **Postman** ou **Insomnia**. Besoin d'un exemple plus avancé ? "" JAX-RS propose plusieurs fonctionnalités avancées qui permettent de développer des services web RESTful robustes et flexibles. Voici quelques-unes des principales fonctionnalités :

1. **Validation des données avec Bean Validation**
   - JAX-RS peut intégrer **Bean Validation** pour vérifier les entrées des requêtes et les réponses des services.

2. **Gestion des sous-ressources**
   - Permet de structurer les API en sous-ressources pour une meilleure modularité.

3. **Intégration avec CDI et EJB**
   - JAX-RS peut être combiné avec **Contexts and Dependency Injection (CDI)** et **Enterprise JavaBeans (EJB)** pour une gestion avancée des dépendances et des transactions.

4. **Requêtes HTTP conditionnelles**
   - Supporte les en-têtes `If-Modified-Since` et `If-None-Match` pour optimiser les échanges de données.

5. **Négociation de contenu dynamique**
   - Permet de choisir le format de réponse (`JSON`, `XML`, etc.) en fonction des préférences du client.

6. **Utilisation de JAXB pour la sérialisation**
   - JAX-RS peut utiliser **JAXB** pour convertir des objets Java en XML et inversement.

Si tu veux un exemple détaillé sur l'une de ces fonctionnalités, dis-moi laquelle t'intéresse ! 😊"


[⬅️ Retour à l'accueil](../index.md)