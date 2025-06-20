# 🟦 Catégorie : Java

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

## ✅ API Stream

L'**API Stream** en Java, introduite avec **Java 8**, permet de traiter des collections de manière **fonctionnelle** et **efficace**. Elle offre une approche déclarative pour manipuler des ensembles de données sans avoir à gérer explicitement les boucles et les itérations.

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
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David");

        List<String> filteredNames = names.stream()
                                          .filter(name -> name.startsWith("C"))
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

Une applet est un programme Java qui s'exécute dans un logiciel de navigation supportant Java ou dans l'appletviewer du JDK.

## ✅ Artifact

En Java, un **artifact** est un fichier produit lors de la compilation et du packaging d'un projet. Il peut s'agir d'une bibliothèque (JAR), d'une application (WAR, EAR) ou d'autres types de fichiers contenant du code ou des ressources.
Les artifacts sont souvent gérés par des systèmes comme **Maven** ou **Gradle**, qui facilitent leur création et leur distribution. Par exemple, avec Maven, un artifact est défini par trois éléments clés :

- **Group ID** : identifie l'organisation ou le projet.
- **Artifact ID** : nom spécifique de l'artifact.
- **Version** : numéro de version.

Dans le contexte du développement, un artifact est essentiel pour partager des modules de code entre différentes applications et équipes.

## ✅ Autoboxing

L'autoboxing en Java est le processus automatique par lequel le compilateur convertit un type primitif (comme int, double, boolean) en son équivalent objet de classe enveloppe (Integer, Double, Boolean). L'opération inverse, appelée unboxing, consiste à convertir un objet de classe enveloppe en son type primitif correspondant. L'autoboxing et l'unboxing permettent d'utiliser les types primitifs et leurs classes enveloppes de manière interchangeable, facilitant l'utilisation des collections et des génériques en Java.

## ✅ Beans

Les JavaBeans sont des composants réutilisables introduits par le JDK 1.1. De nombreuses fonctionnalités ont ensuite été ajoutées pour développer des caractéristiques de ces composants. Les beans sont prévus pour pouvoir interagir avec d'autres beans au point de pouvoir développer une application simplement en assemblant des beans avec un outil graphique dédié. Sun fournit gratuitement un tel outil : le B.D.K. (Bean Development Kit). Des composants réutilisables sont des objets autonomes qui doivent pouvoir être facilement assemblés entres eux pour créer un programme.

Les JavaBeans possèdent plusieurs caractéristiques :

- la persistance : elle permet grâce au mécanisme de sérialisation de sauvegarder l'état d'un bean pour le restaurer. Ainsi si on assemble plusieurs beans pour former une application, on peut la sauvegarder.
la communication, grâce à des événements, qui utilise le modèle des écouteurs introduit par Java 1.1
- l'introspection : ce mécanisme permet de découvrir de façon dynamique l'ensemble des éléments qui composent le bean (attributs, méthodes et événements) sans avoir le code source.
- la possibilité de paramétrer le composant : les données du paramétrage sont conservées dans des propriétés."

## ✅ Collections

Les collections en Java sont un ensemble de classes et d'interfaces qui permettent de stocker, manipuler et organiser des groupes d'objets. Elles font partie du framework Java Collections, qui offre des structures de données flexibles et optimisées pour diverses opérations comme la recherche, le tri, l'insertion et la suppression.

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

Ces cinq structures de données en Java sont utilisées pour stocker et manipuler des collections d'éléments, mais elles ont des caractéristiques différentes qui les rendent adaptées à divers cas d'utilisation. Voici un comparatif :

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

Cet outil est le compilateur : il utilise un fichier source Java fourni en paramètre pour créer un ou plusieurs fichiers contenant le bytecode Java correspondant. Pour chaque fichier source, un fichier portant le même nom avec l'extension .class est créé si la compilation se déroule bien.

## ✅ Enum

Un **`enum`** en Java (abréviation de *enumeration*) est un **type spécial de classe** qui permet de définir un ensemble **de constantes prédéfinies**. Il a été introduit avec Java 5 pour offrir une alternative plus sûre et plus puissante aux constantes `public static final`.

---

### 🧠 Définition

Un `enum` est une classe qui :

- étend implicitement `java.lang.Enum` (donc ne peut pas hériter d’une autre classe),
- contient un ensemble **fini et immuable** de constantes,
- peut avoir des **champs**, **méthodes**, **constructeurs**, et même **implémenter des interfaces**.

Exemple simple :

```java
public enum Couleur {
    ROUGE, VERT, BLEU
}
```

---

### 🧰 Cas d’usage typiques

1. **Limiter les valeurs possibles d’une variable**
   - Ex : jours de la semaine, états d’un processus, types de rôles utilisateur.

2. **Remplacer les constantes `public static final`**
   - Plus lisible, plus sûr, et permet des fonctionnalités supplémentaires.

3. **Utilisation dans les `switch`**
   - Les `enum` peuvent être utilisés dans des instructions `switch`, ce qui les rend pratiques pour la logique conditionnelle.

4. **Associer des données à chaque constante**
   - Exemple : un `enum` `Planete` avec masse et rayon.

```java
public enum Planete {
    TERRE(5.97e24, 6371),
    MARS(6.42e23, 3389);

    private final double masse;
    private final int rayon;

    Planete(double masse, int rayon) {
        this.masse = masse;
        this.rayon = rayon;
    }

    public double getMasse() { return masse; }
    public int getRayon() { return rayon; }
}
```

5. **Utilisation dans les bases de données**
   - Les `enum` sont souvent utilisés pour représenter des colonnes avec des valeurs fixes (ex : statut d’une commande).

---

## ✅ Expressions lambda

Les **expressions lambda** en Java sont une des grandes nouveautés introduites avec **Java 8**. Elles permettent d’écrire du code plus **concise**, **lisible** et **fonctionnel**, en particulier lorsqu’on travaille avec des interfaces fonctionnelles ou l’API Stream.

---

### 🧠 Définition

Une expression lambda est une **fonction anonyme** (c’est-à-dire sans nom) que l’on peut passer comme argument à une méthode. Elle permet de représenter une **interface fonctionnelle**, c’est-à-dire une interface avec **une seule méthode abstraite**.

**Syntaxe générale :**

```java
(paramètres) -> { corps de la fonction }
```

---

### ✨ Exemples

1. **Sans paramètre :**

```java
() -> System.out.println("Hello !");
```

2. **Avec un paramètre :**

```java
x -> x * x
```

3. **Avec plusieurs paramètres :**

```java
(a, b) -> a + b
```

4. **Avec un bloc de code :**

```java
(x, y) -> {
    int result = x + y;
    return result;
}
```

---

### 🧰 Cas d’usage typiques

- **API Stream** :

```java
List<String> noms = List.of("Alice", "Bob", "Charlie");
noms.forEach(n -> System.out.println(n));
```

- **Tri personnalisé** :

```java
Collections.sort(liste, (a, b) -> a.compareToIgnoreCase(b));
```

- **Listeners ou callbacks** :

```java
button.setOnAction(e -> System.out.println("Bouton cliqué !"));
```

---

### 🧩 Interfaces fonctionnelles courantes

Une **interface fonctionnelle** en Java est une interface qui ne contient **qu’une seule méthode abstraite**. Elle est conçue pour représenter une **fonction** que l’on peut passer comme argument, notamment via les **expressions lambda** ou les **références de méthode**.

---

#### 🧠 Définition

```java
@FunctionalInterface
public interface Calculateur {
    int calculer(int a, int b);
}
```

L’annotation `@FunctionalInterface` est facultative mais recommandée : elle garantit que l’interface ne contient qu’une seule méthode abstraite.

---

#### 🧰 Cas d’usage

1. **Expressions lambda**

   ```java
   Calculateur addition = (a, b) -> a + b;
   System.out.println(addition.calculer(3, 4)); // Affiche 7
   ```

2. **API Stream**

   ```java
   List<String> noms = List.of("Alice", "Bob", "Charlie");
   noms.forEach(n -> System.out.println(n));
   ```

3. **Interfaces fonctionnelles prédéfinies**
   Java fournit plusieurs interfaces dans `java.util.function`, comme :
   - `Predicate<T>` : retourne un booléen (`test(T t)`)
   - `Function<T, R>` : transforme un type en un autre (`apply(T t)`)
   - `Consumer<T>` : consomme une valeur sans retour (`accept(T t)`)
   - `Supplier<T>` : fournit une valeur sans paramètre (`get()`)

---

## ✅ Final

Indique qu'une variable ne peut pas être réassignée après son initialisation. Il peut aussi être appliqué aux méthodes (empêchant la surcharge) et aux classes (empêchant l'héritage).

## ✅ Garbage collector

Mécanisme automatique de gestion mémoire qui libère les objets non utilisés pour éviter les fuites mémoire.

## ✅ Generics

Les génériques en Java permettent de créer des classes, interfaces et méthodes qui peuvent fonctionner avec différents types de données tout en garantissant la sécurité du typage à la compilation. Ils ont été introduits dans Java 5 pour éviter les erreurs de conversion de type et améliorer la lisibilité du code.

### 1. Pourquoi utiliser les génériques ?

- Sécurité du typage : Évite les erreurs de conversion (ClassCastException).
- Réutilisation du code : Permet d'écrire des classes et méthodes indépendantes du type de données.
- Lisibilité et maintenabilité : Rend le code plus clair et compréhensible.

### 2. Syntaxe des génériques

Les génériques utilisent des paramètres de type (<T>, <E>, <K, V>, etc.) pour définir des classes ou des méthodes génériques. Les génériques sont essentiels pour écrire du code réutilisable, sécurisé et maintenable en Java.

## ✅ Gestion de la mémoire en Java

La **gestion de la mémoire en Java** repose principalement sur la **JVM (Java Virtual Machine)**, qui s’occupe automatiquement de l’allocation et de la libération de la mémoire via un mécanisme appelé **Garbage Collector (GC)**. Voici les grands principes à connaître :

---

### 🧠 Les zones mémoire principales

1. **Heap (tas)** :  
   - Contient tous les objets créés dynamiquement (`new`).
   - Gérée par le Garbage Collector.
   - Divisée en **Young Generation**, **Old Generation**, et parfois **Metaspace**.

2. **Stack (pile)** :  
   - Contient les variables locales, les appels de méthode, etc.
   - Chaque thread a sa propre pile.
   - Mémoire gérée automatiquement à la fin de chaque méthode.

3. **Metaspace** (depuis Java 8) :  
   - Contient les métadonnées des classes (remplace l’ancien PermGen).

---

### 🧹 Le Garbage Collector (GC)

Le GC libère automatiquement la mémoire des objets **inaccessibles** (plus référencés). Il existe plusieurs algorithmes de GC, comme :

- **Serial GC** : simple, pour les petites applis.
- **Parallel GC** : optimisé pour les performances.
- **G1 GC** : équilibre entre pause courte et efficacité.
- **ZGC / Shenandoah** : pour les très faibles temps de pause.

---

### 🧰 Bonnes pratiques

- **Éviter les fuites mémoire** : même avec un GC, un objet référencé inutilement ne sera pas libéré.
- **Utiliser les collections adaptées** : comme `WeakHashMap` pour des références faibles.
- **Surveiller la mémoire** avec des outils comme `jvisualvm`, `jconsole`, ou des profilers (YourKit, JProfiler...).

---

### 📚 Pour aller plus loin

Ce [chapitre très complet sur la gestion mémoire dans la JVM HotSpot](https://www.jmdoudoux.fr/java/dej/chap-gestion_memoire.htm) ou ce [guide illustré sur la mémoire Java (heap, stack, GC)](https://www.guru99.com/fr/memory-management-in-java.html).

## ✅ Hibernate

Hibernate est une solution open source de type ORM (Object Relational Mapping) qui permet de faciliter le développement de la couche persistance d'une application. Hibernate permet donc de représenter une base de données en objets Java et vice versa. Hibernate facilite la persistence et la recherche de données dans une base de données en réalisant lui-même la création des objets et les traitements de remplissage de ceux-ci en accédant à la base de données. La quantité de code ainsi épargnée est très importante d'autant que ce code est généralement fastidieux et redondant. Hibernate est très populaire notamment à cause de ses bonnes performances et de son ouverture à de nombreuses bases de données. Les bases de données supportées sont les principales du marché : DB2, Oracle, MySQL, PostgreSQL, Sybase, SQL Server, Sap DB, Interbase, ...

## ✅ Histoire de Java

L’histoire du langage Java est une véritable saga technologique, née d’un besoin de simplicité, de portabilité et de sécurité dans un monde informatique en pleine mutation.

---

### 🌱 Les origines (1991–1995)

Java a vu le jour en **1991** sous le nom de code **Oak**, dans les laboratoires de **Sun Microsystems**. L’équipe à l’origine du projet, surnommée la *Green Team*, était dirigée par **James Gosling**, accompagné de Mike Sheridan et Patrick Naughton. Leur objectif ? Créer un langage orienté objet, plus simple que C++, capable de fonctionner sur n’importe quel appareil, indépendamment du système d’exploitation.

Mais le nom *Oak* étant déjà déposé, le langage fut rebaptisé **Java** en 1995 — un clin d’œil au café que buvaient les développeurs pendant leurs longues sessions de codage.

---

### 🚀 Le lancement officiel (1995)

Java est présenté au public le **23 mai 1995** lors de la conférence SunWorld. Il se distingue immédiatement par son slogan révolutionnaire :  
**“Write once, run anywhere”** — *Écris une fois, exécute partout*.  
Grâce à la **machine virtuelle Java (JVM)**, les programmes Java peuvent être exécutés sur n’importe quelle plateforme compatible, sans modification du code.

---

### 📈 L’essor et la maturité (1996–2009)

Java devient rapidement un pilier du développement logiciel :

- **Java 1.0** sort en 1996.
- Il s’impose dans les **applications web** (avec les applets), puis côté **serveur** (avec les servlets et JSP).
- Il est adopté massivement dans les entreprises, les systèmes embarqués, et plus tard dans le développement **Android**.

---

### 🔄 Oracle et l’évolution continue (2009–aujourd’hui)

En **2009**, Oracle rachète Sun Microsystems et prend en charge le développement de Java. Depuis, le langage évolue régulièrement :

- Introduction des **expressions lambda** (Java 8),
- Améliorations de la syntaxe, de la performance et de la sécurité,
- Dernière version majeure : **Java 24**, sortie en mars 2025.

---

Java reste aujourd’hui l’un des langages les plus utilisés au monde, apprécié pour sa robustesse, sa communauté active et sa capacité à évoluer sans perdre son identité.

Voici un aperçu des **versions majeures de Java** qui ont marqué l’évolution du langage depuis sa création :

---

### 🕰️ Versions historiques

- **Java 1.0 (1996)** : Première version publique. Introduction des applets, AWT, et des bases du langage.
- **Java 1.2 (1998)** : Introduction de la **Java Platform, Standard Edition (J2SE)**, Swing, Collections Framework.
- **Java 1.5 (2004)** : Aussi appelée Java 5. Introduction des **génériques**, **annotations**, **enum**, et **autoboxing**.
- **Java 6 (2006)** : Améliorations de performance, support de scripting via l’API javax.script.

---

### 🚀 Versions modernes

- **Java 7 (2011)** : Syntaxe améliorée (try-with-resources, switch sur String), NIO.2.
- **Java 8 (2014)** : Révolution majeure avec les **expressions lambda**, **Stream API**, et **Optional**. Encore très utilisée aujourd’hui.
- **Java 9 (2017)** : Introduction du **système de modules (Project Jigsaw)**.
- **Java 11 (2018)** : Version **LTS (Long-Term Support)**. Ajout de `var` pour les variables locales, API HTTP Client.
- **Java 17 (2021)** : Autre version LTS. Ajout des **records**, **sealed classes**, et améliorations de la JVM.
- **Java 21 (2023)** : LTS récente. Intègre des fonctionnalités comme les **threads virtuels (Project Loom)**, **pattern matching**, et **structured concurrency**.
- **Java 24 (2025)** : Dernière version à ce jour. Consolidation des nouveautés précédentes, avec des optimisations JVM et des raffinements syntaxiques.

---

Depuis Java 9, Oracle publie une nouvelle version **tous les 6 mois**, mais seules certaines versions sont **LTS**, c’est-à-dire maintenues à long terme (Java 8, 11, 17, 21).

## ✅ Immutabilité

En Java, l'immutabilité est un concept clé qui garantit qu'un objet ne peut pas être modifié après sa création. Cela améliore la sécurité, la performance et la gestion de la concurrence.
Exemples d'objets immuables en Java :

- String : Une fois créée, une chaîne de caractères ne peut pas être modifiée.
- Integer, BigDecimal, LocalDate : Ces classes sont conçues pour être immuables.

### Comment créer une classe immuable ?

- Déclarer la classe final pour empêcher l'héritage.
- Définir tous les champs comme private final pour éviter leur modification.
- Ne pas fournir de setters, seulement des getters.

### Utiliser des copies défensives pour les objets mutables.  Avantages de l'immutabilité

- Sécurité : Évite les modifications accidentelles.
- Thread-safe : Aucun risque de corruption des données en environnement concurrent.
- Optimisation : Peut être mis en cache et réutilisé efficacement.

## ✅ Introspection

L’introspection désigne la capacité d'un programme à analyser dynamiquement les propriétés et les méthodes d’un objet à l’exécution. Java offre des mécanismes permettant de découvrir ces informations sans connaître à l’avance la structure exacte de la classe. Cas d'usage : ORM (Hibernate, JPA) : Les ORM utilisent l’introspection pour cartographier les Beans avec une base de données sans écrire de code spécifique pour chaque classe. ✔ API REST et JSON : Transformer dynamiquement des Beans en JSON/XML pour une communication inter-systèmes. ✔ Bibliothèques UI : Génération automatique d'interfaces à partir des Beans, permettant une adaptation sans code statique.

## ✅ Interopérabilité

L’interopérabilité signifie que les composants (ici, les Beans) peuvent être utilisés sur différentes plateformes ou systèmes sans modification majeure.
Dans le contexte des Beans :
Un Java Bean sérialisé peut être envoyé sur un réseau et lu par un autre programme, même s'il tourne sur un autre système.
Les JSON/XML Beans sont souvent utilisés pour échanger des données entre une application Java et d’autres technologies (JavaScript, Python, etc.).
Spring Beans et REST API permettent d’exposer des objets sous forme de services web, accessibles par différentes applications.

## ✅ Interpréteur java/javaw

Ces deux outils sont les interpréteurs de bytecode : ils lancent le JRE, chargent les classes nécessaires et exécutent la méthode main de la classe passée en paramètre. java ouvre une console pour recevoir les messages de l'application alors que javaw n'en ouvre pas.

## ✅ J2EE

J2EE est l'acronyme de Java 2 Entreprise Edition. Cette édition est dédiée à la réalisation d'applications pour entreprises. J2EE est basé sur J2SE (Java 2 Standard Edition) qui contient les API de base de Java. Depuis sa version 5, J2EE est renommée Java EE (Enterprise Edition).

## ✅ JAX-RS

JAX-RS est une API Java conçue pour développer des services web RESTful. Elle permet de gérer des requêtes HTTP et d'exposer des ressources via des annotations simples. Voici quelques points clés :

- **Méthodes HTTP** : JAX-RS prend en charge les méthodes **GET, POST, PUT, DELETE** pour interagir avec les ressources.
- **Annotations** :
  - `@Path("/resource")` : Définit l'URI de la ressource.
  - `@GET`, `@POST`, `@PUT`, `@DELETE` : Spécifie la méthode HTTP utilisée.
  - `@Produces("application/json")` : Indique le format de réponse.
  - `@Consumes("application/json")` : Définit le format des données reçues.

Exemple de requête GET avec JAX-RS :

```java
import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;
import jakarta.ws.rs.Produces;
import jakarta.ws.rs.core.MediaType;

@Path("/hello")
public class HelloResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String sayHello() {
        return "Bonjour, JAX-RS !";
    }
}
```

Tu peux tester cette API avec un client HTTP comme **Postman** ou **Insomnia**. Besoin d'un exemple plus avancé ? 😊

JAX-RS propose plusieurs fonctionnalités avancées qui permettent de développer des services web RESTful robustes et flexibles. Voici quelques-unes des principales fonctionnalités :

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

Si tu veux un exemple détaillé sur l'une de ces fonctionnalités, dis-moi laquelle t'intéresse ! 😊

## ✅ jar

JAR est le diminutif de Java ARchive. C'est un format de fichier qui permet de regrouper des fichiers contenant du bytecode Java (fichier .class) ou des données utilisées en tant que ressources (images, son, ...). Ce format est compatible avec le format ZIP : les fichiers contenus dans un jar sont compressés de façon indépendante du système d'exploitation.

## ✅ Javadoc

Javadoc est un outil fourni avec le JDK pour permettre la génération d'une documentation technique à partir du code source. Cet outil génère une documentation au format HTML à partir du code source Java et des commentaires particuliers qu'il contient. Un exemple concret de l'utilisation de cet outil est la documentation du JDK qui est générée grâce à Javadoc.

## ✅ Java Platform

La Java Platform est un environnement logiciel complet qui permet de développer, compiler et exécuter des applications Java sur divers systèmes d'exploitation. Voici ses éléments clés :

- **Java Virtual Machine (JVM) :** C’est le moteur d’exécution qui interprète le bytecode généré par le compilateur Java. Grâce à la JVM, le même programme peut tourner sur plusieurs plateformes sans modification, d’où le principe "Write Once, Run Anywhere".

- **Bibliothèques et API :** La plateforme inclut un ensemble de bibliothèques standard qui offrent des fonctionnalités prêtes à l’emploi pour la manipulation de collections, la gestion des entrées/sorties, le développement réseau, l’internationalisation, et bien plus. Ces outils facilitent grandement le développement d’applications robustes.

- **Éditions de la plateforme :**  
  - **Java Standard Edition (Java SE) :** La version de base qui sert aussi bien pour développer des applications desktop que pour réaliser des outils divers.  
  - **Java Enterprise Edition (Java EE), désormais Jakarta EE :** Conçue pour les applications d’entreprise, elle intègre des fonctionnalités supplémentaires comme les servlets, la gestion des transactions, et le support web.  
  - **Java Micro Edition (Java ME) :** Adaptée aux appareils embarqués et aux environnements aux ressources limitées, comme certains smartphones ou systèmes embarqués.  
  - **JavaFX :** Utilisée pour créer des interfaces utilisateur modernes et riches.

En résumé, la Java Platform offre non seulement un langage (Java) mais également un écosystème complet qui favorise le développement de logiciels portables, performants et sécurisés. Ce concept de plateforme met l’accent sur l’interopérabilité et la polyvalence, permettant aux développeurs de créer des applications qui fonctionnent de manière identique sur plusieurs environnements, tout en bénéficiant d’un vaste ensemble de bibliothèques et d’outils pour accélérer et sécuriser le développement.

Selon Wikipedia, la dénomination "Java Platform" désigne en réalité l'ensemble des composants (JVM, bibliothèques standards, outils de développement) qui constituent l’environnement d’exécution et le framework de base permettant d’exécuter des applications écrites en Java[^6^].

## ✅ JDBC

JDBC (Java Database Connectivity) est une API Java qui permet aux applications de se connecter à une base de données et d'exécuter des requêtes SQL. Elle offre une interface standardisée pour interagir avec différents systèmes de gestion de bases de données (SGBD) via des pilotes JDBC spécifiques.
JDBC fonctionne en utilisant des pilotes qui traduisent les appels Java en commandes compréhensibles par la base de données. Il existe plusieurs types de pilotes JDBC, allant des pilotes reliant JDBC à ODBC aux pilotes natifs qui communiquent directement avec la base de données."

## ✅ JDK

Le JDK de Sun/Oracle fournit un ensemble d'outils qui permettent de réaliser des applications. Ces outils sont peu ergonomiques car ils s'utilisent en ligne de commandes mais, en contrepartie, ils peuvent toujours être utilisés.

## ✅ JPA

API Java Persistence - L'utilisation pour la persistance d'un mapping O/R permet de proposer un niveau d'abstraction plus élevé que la simple utilisation de JDBC : ce mapping permet d'assurer la transformation d'objets  vers la base de données et vice versa que cela soit pour des lectures ou des mises à jour (création, modification ou suppression). L'API propose un langage d'interrogation similaire à SQL mais utilisant des objets plutôt que des entités relationnelles de la base de données. L'API Java Persistence repose sur des entités qui sont de simples POJOs annotés et sur un gestionnaire de ces entités (EntityManager) qui propose des fonctionnalités pour les manipuler (ajout, modification suppression, recherche). Ce gestionnaire est responsable de la gestion de l'état des entités et de leur persistance dans la base de données.

## ✅ JRE

Le JRE (Java Runtime Environment) est un environnement d'exécution qui permet d'exécuter des programmes écrits en langage Java. Il comprend une machine virtuelle Java (JVM), des bibliothèques logicielles et un plugin permettant l'exécution des programmes Java depuis les navigateurs web. Le JRE est souvent installé sur les ordinateurs pour garantir la compatibilité des applications Java avec différents systèmes d'exploitation2.

## ✅ JVM

La machine virtuelle Java ou JVM (Java Virtual Machine) est un environnement d'exécution pour applications Java.
C'est un des éléments les plus importants de la plate-forme Java. Elle assure l'indépendance du matériel et du système d'exploitation lors de l'exécution des applications Java. Une application Java ne s'exécute pas directement dans le système d'exploitation mais dans une machine virtuelle qui s'exécute dans le système d'exploitation et propose une couche d'abstraction entre l'application Java et ce système.
La machine virtuelle permet notamment :

- l'interprétation du bytecode
- l'interaction avec le système d'exploitation
- la gestion de sa mémoire grâce au ramasse-miettes
Son mode de fonctionnement est relativement similaire à celui d'un ordinateur : elle exécute des instructions qui manipulent différentes zones de mémoire dédiées de la JVM.
Une application Java ne fait pas d'appel direct au système d'exploitation (sauf en cas d'utilisation de JNI) : elle n'utilise que les API qui sont pour une large part écrites en Java sauf quelques-unes qui sont natives. Ceci permet à Java de rendre les applications indépendantes de l'environnement d'exécution.
La machine virtuelle ne connaît pas le langage Java : elle ne connaît que le bytecode qui est issu de la compilation de codes sources écrits en Java.
Les spécifications de la machine virtuelle Java définissent :
- Les concepts du langage Java
- Le format des fichiers .class
- Les fonctionnalités de la JVM
- Le chargement des fichiers .class
- Le bytecode
- La gestion des threads et des accès concurrents
- ...
Les fonctionnalités de la JVM décrites dans les spécifications sont abstraites : elles décrivent les fonctionnalités requises mais ne fournissent aucune implémentation ou algorithme d'implémentation. L'implémentation est à la charge du fournisseur de la JVM. Il existe de nombreuses implémentations de JVM dont les plus connues sont celles de Sun Microsystems/Oracle (HotSpot), IBM (J9), BEA/Oracle (JRockit), Azul (Zing), ...
Le respect strict de ces spécifications par une implémentation de la JVM garantit la portabilité et la bonne exécution du bytecode.
Ces spécifications sont consultables à l'url : <https://docs.oracle.com/javase/specs/>

## ✅ La gestion des exceptions en Java

En Java, la gestion des **exceptions** est un mécanisme fondamental qui permet de gérer les erreurs et comportements inattendus **à l'exécution**.

---

### 🔹 **1. Qu’est-ce qu’une exception ?**

Une **exception** est un événement qui interrompt le flux normal d’un programme lorsque quelque chose ne se passe pas comme prévu (ex. : division par zéro, fichier introuvable).

---

### 🔹 **2. Hiérarchie des exceptions**

Toutes les exceptions dérivent de la classe `Throwable` :

```plaintext
Object
└── Throwable
    ├── Error          (problèmes système graves)
    └── Exception
        ├── CheckedException  (à traiter obligatoirement)
        └── UncheckedException (RuntimeException : pas obligatoire à traiter)
```

- **Checked Exception** : Exception vérifiée à la compilation (ex : `IOException`, `SQLException`).
- **Unchecked Exception** : Non vérifiée (ex : `NullPointerException`, `ArithmeticException`).

---

### 🔹 **3. Bloc try-catch-finally**

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Erreur : division par zéro !");
} finally {
    System.out.println("Bloc finally exécuté quoi qu’il arrive.");
}
```

- `try` : Bloc contenant le code susceptible de générer une exception.
- `catch` : Bloc de traitement de l’exception.
- `finally` : Bloc optionnel, toujours exécuté (même après `return`).

---

### 🔹 **4. Le mot-clé `throw`**

Permet de **lancer manuellement** une exception :

```java
throw new IllegalArgumentException("Argument invalide");
```

---

### 🔹 **5. Le mot-clé `throws`**

Permet de **déclarer** qu’une méthode peut générer une exception :

```java
public void lireFichier() throws IOException {
    // code qui peut lancer IOException
}
```

---

### 🔹 **6. Exceptions personnalisées**

Créer sa propre exception :

```java
public class MonException extends Exception {
    public MonException(String message) {
        super(message);
    }
}
```

Utilisation :

```java
throw new MonException("Erreur spécifique");
```

---

### 🔹 **7. Bonnes pratiques**

✅ Ne pas attraper une exception sans la traiter (`catch(Exception e) {}` = 🚫)  
✅ Utiliser des messages explicites  
✅ Privilégier les exceptions spécifiques  
✅ Nettoyer les ressources dans `finally` ou utiliser `try-with-resources` pour l’I/O

---

Parfait ! Voici **les deux compléments** pour mieux comprendre la gestion des exceptions en Java :

---

### 🔹 **Exemple interactif complet**

Un exemple de gestion de plusieurs types d’exceptions avec `try-catch`, `finally`, `throw` et `throws`.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ExempleGestionExceptions {

    public static void main(String[] args) {
        try {
            lireFichier("inexistant.txt");
            int resultat = division(10, 0); // provoque ArithmeticException
            System.out.println("Résultat : " + resultat);
        } catch (IOException e) {
            System.out.println("Erreur de fichier : " + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("Erreur arithmétique : " + e.getMessage());
        } catch (Exception e) {
            System.out.println("Erreur générale : " + e.getMessage());
        } finally {
            System.out.println("Fin du programme.");
        }
    }

    public static void lireFichier(String nomFichier) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader(nomFichier));
        String ligne;
        while ((ligne = br.readLine()) != null) {
            System.out.println(ligne);
        }
        br.close();
    }

    public static int division(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Division par zéro interdite");
        }
        return a / b;
    }
}
```

---

## 🔹 Résumé des concepts utilisés

| Élément                              | Utilisation                           |
| ------------------------------------ | ------------------------------------- |
| `try`                                | Code à risque                         |
| `catch`                              | Capture et traitement d'une exception |
| `finally`                            | Exécuté dans tous les cas (nettoyage) |
| `throw`                              | Lancer une exception manuellement     |
| `throws`                             | Déclare une exception potentielle     |
| `IOException`, `ArithmeticException` | Exceptions spécifiques                |

---

## ✅ Maven

Maven est un outil de construction de projets (build) open source développé par la fondation Apache, initialement pour les besoins du projet Jakarta Turbine. Il permet de faciliter et d'automatiser certaines tâches de la gestion d'un projet Java.

## ✅ Optional

La classe `Optional<T>` est un conteneur introduit avec Java 8 pour représenter de manière explicite la possibilité qu'une valeur soit présente ou non, plutôt que de recourir aux références null. Cela permet d'éviter de nombreux problèmes liés aux NullPointerExceptions et rend le code plus lisible en forçant l'appelant à gérer le cas d'une valeur absente. [^3^][^4^]

### Création d'un `Optional`

Il existe plusieurs façons de créer un `Optional` :

- **Avec une valeur garantie non nulle :**

  ```java
  Optional<String> opt = Optional.of("Hello");
  ```

  Utilisez `of` lorsque vous êtes certain que la valeur n'est pas nulle. Sinon, cette méthode lèvera une `NullPointerException`.

- **Avec une valeur potentiellement nulle :**

  ```java
  Optional<String> optNullable = Optional.ofNullable(null);
  ```

  Grâce à `ofNullable`, si la valeur passée est nulle, l'`Optional` sera vide.

- **Pour représenter explicitement l'absence d'une valeur :**

  ```java
  Optional<String> emptyOpt = Optional.empty();
  ```

  Ceci crée un `Optional` vide. [^3^]

### Utilisation d'`Optional` dans vos méthodes

Plutôt que de retourner directement une valeur qui peut être nulle, vous pouvez retourner un `Optional`. Par exemple :

```java
public Optional<String> getUserNameById(String id) {
    String username = /* logique pour récupérer le nom d’utilisateur */;
    return Optional.ofNullable(username);
}
```

L'appelant devra ensuite gérer le cas du vide :

```java
Optional<String> usernameOpt = getUserNameById("123");

usernameOpt.ifPresent(u -> System.out.println("Nom d'utilisateur : " + u));
// ou
String username = usernameOpt.orElse("Utilisateur inconnu");
System.out.println(username);
```

### Méthodes courantes

Parmi les méthodes les plus utilisées sur un `Optional`, on retrouve :

- **isPresent() et isEmpty()**  
  Permettent de savoir si une valeur est contenue dans l'`Optional`.

- **ifPresent(Consumer<? super T> action)**  
  Exécute l'action donnée si la valeur est présente.

- **orElse(T other)**  
  Retourne la valeur si présente, sinon retourne la valeur par défaut.

- **orElseGet(Supplier<? extends T> supplier)**  
  Semblable à `orElse`, mais la valeur par défaut est générée à la demande (ce qui peut éviter de coûteux calculs inutiles).

- **orElseThrow()** ou **orElseThrow(Supplier<? extends X> exceptionSupplier)**  
  Permet de lever une exception si aucune valeur n'est présente.

- **map(Function<? super T, ? extends U> mapper)** et **flatMap(Function<? super T, Optional<U>> mapper)**  
  Pour transformer la valeur contenue dans l'`Optional` de manière fluide, tout en gérant la possibilité d'une absence de valeur.

Par exemple, pour transformer et filtrer une valeur :

```java
Optional<String> opt = Optional.of("java");
Optional<String> upperOpt = opt.map(String::toUpperCase);
    
upperOpt.ifPresent(System.out::println);  // Affichera "JAVA"
```

### Bonnes pratiques

- **Utilisation en sortie (retour de méthode) :**  
  Il est recommandé d'utiliser `Optional` comme type de retour des méthodes, afin de signaler clairement qu'une valeur peut être absente.

- **Attention à l'usage en tant que champ ou paramètre :**  
  De nombreux experts (comme Brian Goetz) recommandent de n'utiliser `Optional` ni pour les paramètres de méthodes ni pour les attributs de classes, afin d'éviter une surcomplexification du code. [^3^]

- **Chaînage d'opérations :**  
  Les méthodes comme `map`, `flatMap` et `filter` permettent d'écrire un code fluide et fonctionnel sans avoir à vérifier constamment si la valeur existe. [^4^]

En résumé, `Optional` est une excellente façon de rendre vos méthodes plus sûres et vos intentions plus explicites quant à la possibilité d'absence de résultat. En l'utilisant, vous forcez le développeur appelant à traiter le cas où la donnée n'est pas présente et vous réduisez ainsi le risque d'erreurs liées aux valeurs nulles.

## ✅ POJO

Un POJO (Plain Old Java Object) est un objet Java simple qui ne dépend d'aucun framework spécifique. Il est utilisé pour représenter des données de manière indépendante, sans imposer de contraintes particulières comme l'implémentation d'interfaces ou l'héritage de classes spécifiques.
L'idée derrière les POJO est de garder les objets Java aussi simples que possible, facilitant ainsi leur réutilisation et leur lisibilité dans un programme. Contrairement aux JavaBeans, qui doivent être sérialisables et suivre certaines conventions (comme avoir un constructeur sans argument et des méthodes getter/setter), un POJO est plus libre dans sa structure.

## ✅ Primitifs

En Java, les types primitifs sont des types de données de base qui ne sont pas des objets. Ils sont utilisés pour stocker des valeurs simples et sont plus efficaces en termes de mémoire et de performance que les objets. Java définit huit types primitifs :

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

## ✅ Programmation orientée aspect

(AOP - Aspect-Oriented Programming) : Permet de séparer les préoccupations transversales (logging, sécurité, transactions).

## ✅ 🧵 Programmation parralèle et concurente

## 🧩 Concepts clés

- **Concurrence** : plusieurs tâches s'exécutent **indépendamment** dans un environnement multitâche. Utilisé pour améliorer la **réactivité** (ex: interface utilisateur, serveurs web).
- **Parallélisme** : plusieurs tâches s'exécutent **simultanément** sur plusieurs processeurs/coeurs. Utilisé pour accélérer le **traitement de données**.

---

## ✅ APIs et Outils principaux

### 1. `Thread` (de base)

```java
class MonThread extends Thread {
    public void run() {
        System.out.println("Tâche dans MonThread");
    }
}

public class Main {
    public static void main(String[] args) {
        MonThread t = new MonThread();
        t.start();
    }
}
```

### 2. `Runnable` avec `Thread`

```java
Runnable task = () -> System.out.println("Tâche dans Runnable");
Thread thread = new Thread(task);
thread.start();
```

### 3. `ExecutorService` (pool de threads)

```java
ExecutorService executor = Executors.newFixedThreadPool(2);

executor.submit(() -> {
    System.out.println("Tâche asynchrone avec pool");
});

executor.shutdown();
```

### 4. `Callable` et `Future`

```java
Callable<Integer> task = () -> 21 + 21;
Future<Integer> future = executor.submit(task);
System.out.println("Résultat : " + future.get()); // get() bloque
```

### 5. `ForkJoinPool`

```java
ForkJoinPool pool = new ForkJoinPool();

int result = pool.invoke(new RecursiveTask<Integer>() {
    protected Integer compute() {
        return 40 + 2;
    }
});
System.out.println("Résultat ForkJoin : " + result);
```

### 6. `CompletableFuture` (Java 8+)

```java
CompletableFuture.supplyAsync(() -> 40)
    .thenApply(x -> x + 2)
    .thenAccept(System.out::println);
```

---

## 🔁 Collections Concurrentes

- `ConcurrentHashMap`
- `CopyOnWriteArrayList`
- `BlockingQueue`, `ArrayBlockingQueue`, `LinkedBlockingQueue`

---

## 🧰 Outils de synchronisation

- `synchronized`
- `Lock`, `ReentrantLock`
- `CountDownLatch`
- `Semaphore`
- `CyclicBarrier`
- `ReadWriteLock`

---

## 🚨 Problèmes fréquents

| Problème           | Description |
|--------------------|-------------|
| Condition de course | Deux threads modifient la même donnée en même temps |
| Deadlock            | Deux threads attendent mutuellement une ressource |
| Starvation          | Un thread n'obtient jamais de ressources |
| Livelock            | Les threads s'activent sans faire de progrès utile |

---

## ✅ Bonnes pratiques

- Utiliser `Executors` au lieu de créer les threads manuellement.
- Préférer `CompletableFuture` pour la lisibilité et la gestion fluide des erreurs.
- Éviter les blocs `synchronized` imbriqués.
- Tester avec des outils comme **JMH** ou **VisualVM**.

---

## 📚 Ressources recommandées

- *Java Concurrency in Practice* – Brian Goetz
- [Oracle Concurrency Tutorial](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- [Baeldung – Java Concurrency](https://www.baeldung.com/java-concurrency)

## ✅ Record

En Java, un **`record`** est un type spécial de classe introduit en Java 14 (en aperçu) et standardisé en Java 16. Il permet de déclarer de manière **concise et immuable** des classes qui servent principalement à **transporter des données**.

---

### 🧠 Définition

Un `record` est une classe **finale**, **immutable**, et **orientée données**. Il génère automatiquement :

- un **constructeur** avec tous les champs,
- des **getters** (sans le préfixe `get`),
- les méthodes `equals()`, `hashCode()` et `toString()`.

Exemple :

```java
public record Personne(String nom, String prenom) {}
```

Cela équivaut à une classe avec deux champs `final`, un constructeur, deux getters, et les méthodes `equals`, `hashCode`, `toString`.

---

### ✅ Avantages

- **Moins de code boilerplate** (pas besoin d’écrire manuellement les méthodes usuelles).
- **Immutabilité garantie** : les champs sont `private final`.
- **Lisibilité accrue** : on comprend immédiatement que la classe est une simple structure de données.

---

### 🔒 Limitations

- Un `record` **ne peut pas hériter** d’une autre classe.
- Il **ne peut pas avoir d’autres champs d’instance** que ceux définis dans sa déclaration.
- Il **ne peut pas être abstrait**.

---

### 🧰 Cas d’usage typiques

- Transfert de données entre couches (DTO).
- Résultats de requêtes.
- Clés ou valeurs dans des collections.
- Représentation d’un état ou d’un événement.

## ✅ Sérialisation

La sérialisation en Java consiste à convertir un objet en un format pouvant être stocké ou transmis (ex. un fichier, un flux réseau, une base de données). Cela permet de conserver l’état d’un objet et de le restaurer plus tard.

## ✅ Static

Indique qu'une variable ou une méthode appartient à la classe elle-même plutôt qu'à une instance spécifique. Cela signifie qu'il n'est pas nécessaire de créer un objet pour y accéder.

## ✅ Static Final

Lorsque ces deux mots-clés sont combinés (static final), cela signifie que la variable est une constante de classe, accessible sans instanciation et dont la valeur ne peut pas être modifiée. Pourquoi utiliser static final ?

- Améliore la lisibilité du code en définissant des valeurs constantes.
- Optimise la gestion de la mémoire en évitant la duplication des valeurs.
- Facilite la maintenance en centralisant les constantes. L'utilisation de static final en Java est recommandée dans plusieurs cas où une valeur doit rester constante et être partagée entre toutes les instances d'une classe

## ✅ Test

En Java, le **test** est une étape essentielle du développement logiciel pour garantir que le code fonctionne comme prévu. Il existe plusieurs types de tests, chacun avec ses outils et objectifs :

---

### 🧪 **1. Tests unitaires**

Ils vérifient le comportement d’une **méthode ou d’une classe isolée**.

- **Outils populaires** : [JUnit](https://codegym.cc/fr/groups/posts/fr.191.tests-unitaires-en-java-avec-junit), [TestNG](https://codegym.cc/fr/groups/posts/fr.191.tests-unitaires-en-java-avec-junit)
- **Exemple avec JUnit** :

  ```java
  @Test
  void testAddition() {
      assertEquals(4, addition(2, 2));
  }
  ```

---

### 🔗 **2. Tests d’intégration**

Ils testent l’interaction entre plusieurs composants (ex. : service + base de données).

- **Outils** : Spring Test, Arquillian
- **Exemple** : tester un contrôleur REST avec Spring Boot

---

### 🧰 **3. Tests de simulation (Mocking)**

Ils permettent de simuler des dépendances pour tester une unité isolément.

- **Outils** : Mockito, EasyMock
- **Exemple** :

  ```java
  when(service.getData()).thenReturn("mocked");
  ```

---

### 🧼 **4. Tests de bout en bout (E2E)**

Ils simulent un scénario utilisateur complet.

- **Outils** : Selenium (pour les interfaces web), Cucumber (BDD)

---

### 📈 **5. Tests de performance**

Pour mesurer la rapidité et la robustesse du code.

- **Outils** : JMH, JMeter, Gatling

---

### 📚 Pour aller plus loin

Tu peux consulter ce [guide complet sur les tests unitaires en Java](https://zestedesavoir.com/tutoriels/274/les-tests-unitaires-en-java/) ou ce [tutoriel sur JUnit et Mockito](https://javanais.fr/maitriser-junit-guide-complet-pour-les-tests-unitaires-en-java/) pour approfondir.

---

### 🧪 **JUnit** – Le framework de test unitaire

**JUnit** permet d’écrire des tests pour vérifier le comportement de méthodes Java. Depuis JUnit 5, on utilise des annotations comme :

- `@Test` : indique une méthode de test.
- `@BeforeEach` / `@AfterEach` : exécutées avant/après chaque test.
- `@BeforeAll` / `@AfterAll` : exécutées une seule fois pour toute la classe.
- `@DisplayName` : donne un nom lisible au test.

**Exemple simple :**

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class CalculatriceTest {

    @Test
    void testAddition() {
        Calculatrice calc = new Calculatrice();
        assertEquals(5, calc.add(2, 3));
    }
}
```

---

### 🧰 **Mockito** – Simuler des dépendances

**Mockito** permet de créer des objets simulés (mocks) pour tester une classe indépendamment de ses dépendances.

#### Exemple : tester un service avec une dépendance

Imaginons deux classes :

```java
public class AdditionService {
    public int add(int a, int b) {
        return a + b;
    }
}

public class CalculatriceService {
    private final AdditionService additionService;

    public CalculatriceService(AdditionService additionService) {
        this.additionService = additionService;
    }

    public int additionner(int a, int b) {
        return additionService.add(a, b);
    }
}
```

#### Test avec Mockito et JUnit 5

```java
import org.junit.jupiter.api.Test;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.junit.jupiter.MockitoExtension;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.extension.ExtendWith;

@ExtendWith(MockitoExtension.class)
class CalculatriceServiceTest {

    @Mock
    AdditionService additionService;

    @InjectMocks
    CalculatriceService calculatriceService;

    @Test
    void testAdditionner() {
        when(additionService.add(10, 20)).thenReturn(30);

        int result = calculatriceService.additionner(10, 20);

        assertEquals(30, result);
        verify(additionService).add(10, 20);
    }
}
```

---

### 🧠 Ce qu’on apprend ici

- `@Mock` crée un faux objet.
- `@InjectMocks` injecte ce faux dans la classe testée.
- `when(...).thenReturn(...)` définit le comportement attendu.
- `verify(...)` s’assure que la méthode a bien été appelée.

---

Tu veux aller plus loin avec des tests d’exception, des mocks plus complexes ou l’intégration avec Spring Boot ? Je peux aussi te montrer comment tester des appels REST ou des bases de données simulées. 😄  
Sinon, tu peux explorer [cet exemple complet sur Java Guides](https://www.javaguides.net/2023/10/mockito-junit-5-example.html) ou [ce tutoriel pas à pas sur Java Code Geeks](https://examples.javacodegeeks.com/java-development/core-java/mockito/junit-mockito-example/).

## ✅ Thread

La **gestion des threads** en Java est essentielle pour exécuter plusieurs tâches en parallèle et optimiser les performances des applications. Java propose plusieurs mécanismes pour créer et gérer des threads efficacement.

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
           System.out.println("Thread en cours d'exécution !");
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
           System.out.println("Thread via Runnable !");
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

## ✅ 📦 Packages Standards en Java

Un aperçu complet des principaux packages de la bibliothèque standard Java avec des exemples et cas d’usage.

---

### ✅ `java.lang` – Fondamentaux du langage

| Classe              | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `Object`            | Classe racine de toutes les classes Java         | `toString()`, `equals()` |
| `String`            | Chaînes de caractères                            | `"Bonjour".length()` |
| `Math`              | Fonctions mathématiques                          | `Math.sqrt(9)` |
| `System`            | Entrée/sortie système                            | `System.out.println("Hello")` |
| `Thread`            | Thread (concurrence)                             | `new Thread(runnable).start()` |

---

### ✅ `java.util` – Utilitaires

| Classe / Interface  | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `ArrayList`         | Liste dynamique                                  | `new ArrayList<>()` |
| `HashMap`           | Paires clé-valeur                                | `map.get("clé")` |
| `HashSet`           | Ensemble sans doublons                           | `new HashSet<>()` |
| `Date`              | Date/heure (ancien, remplacé par java.time)      | `new Date()` |
| `Random`            | Générateur de nombres aléatoires                 | `new Random().nextInt(10)` |

---

### ✅ `java.io` – Entrées / Sorties

| Classe              | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `File`              | Représente un fichier                            | `new File("chemin.txt")` |
| `BufferedReader`    | Lecture efficace de texte                        | `new BufferedReader(new FileReader(...))` |
| `InputStream`       | Flux d'entrée binaire                            | `System.in.read()` |
| `Serializable`      | Sérialisation d’objets                           | `implements Serializable` |

---

### ✅ `java.net` – Réseau

| Classe              | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `URL`               | Représente une URL                               | `new URL("https://...")` |
| `Socket`            | Communication côté client                        | `new Socket("localhost", 80)` |
| `ServerSocket`      | Écoute côté serveur                              | `new ServerSocket(8080)` |
| `HttpURLConnection` | Requête HTTP                                     | `url.openConnection()` |

---

### ✅ `java.sql` – Accès base de données (JDBC)

| Classe              | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `Connection`        | Connexion BDD                                    | `DriverManager.getConnection(...)` |
| `Statement`         | Requête SQL simple                               | `stmt.executeQuery("SELECT ...")` |
| `PreparedStatement` | Requête paramétrée                               | `stmt.setString(1, "nom")` |
| `ResultSet`         | Résultat d’une requête SQL                       | `rs.getString("col")` |

---

### ✅ `java.time` – Date et heure modernes (Java 8+)

| Classe              | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `LocalDate`         | Date sans heure                                  | `LocalDate.now()` |
| `LocalDateTime`     | Date + Heure sans fuseau                         | `LocalDateTime.now()` |
| `ZonedDateTime`     | Date + heure avec fuseau                         | `ZonedDateTime.now()` |
| `DateTimeFormatter` | Formatage des dates                              | `formatter.format(date)` |

---

### ✅ `javax.*` – Extensions Java

| Package             | Description                                      | Exemple |
|---------------------|--------------------------------------------------|---------|
| `javax.swing`       | Interfaces graphiques                            | `new JFrame("Fenêtre")` |
| `javax.servlet`     | Composants web pour serveurs                     | `HttpServlet` |
| `javax.persistence` | Persistance JPA                                  | `@Entity`, `@Id` |
| `javax.validation`  | Validation des beans                             | `@NotNull`, `@Size` |

---

### ✅ Autres packages utiles

| Package                  | Description                                      |
|---------------------------|--------------------------------------------------|
| `java.nio`               | Nouvelles I/O (fichiers, buffers)                |
| `java.security`          | Cryptographie, certificats                       |
| `java.lang.reflect`      | Réflexion sur les classes                        |
| `java.util.concurrent`   | Programmation concurrente avancée               |

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
