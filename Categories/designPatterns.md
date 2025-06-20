# 🟦 Catégorie : Design patterns

## ✅  Builder

Le design pattern Builder est un modèle de conception créationnel qui permet de construire des objets complexes étape par étape. Il est utile lorsque l’instanciation d’un objet nécessite plusieurs paramètres et configurations, rendant le constructeur classique peu pratique. Comment ça fonctionne ?

- On définit une classe interne PersonBuilder avec des méthodes chaînées.
- Chaque méthode modifie une propriété et retourne this pour permettre la fluidité.
- La méthode build() crée l’objet final et le renvoie.

## ✅  Composite

Le design pattern Composite est un modèle de conception structurel qui permet de traiter les objets et leurs compositions de manière uniforme. Il est particulièrement utile lorsque nous avons une hiérarchie d'objets, où certains objets peuvent contenir d'autres objets. L'idée clé est de permettre aux objets individuels et aux objets composés d'être manipulés de la même manière grâce à une interface commune.

## ✅  Design pattern

Solution éprouvée et réutilisable pour résoudre des problèmes courants dans la conception logicielle.

## ✅ Factory

Le design pattern Factory est un modèle de conception créationnel qui permet d'instancier des objets sans exposer directement leur construction. Il est particulièrement utile lorsqu'on veut centraliser la logique de création et éviter d'utiliser le mot-clé new partout dans le code. Composants : Interface Produit + Classes qui implémentent Produit + Class Factory qui return New ClassesProduits. Variante avec le Design pattern Factory Abstract : Une Interface Produit et ses implémentations, Une interface Factory et ses implémentations qui utilisent les implémentations de Produit.

## ✅  Observer

Le design pattern Observer est un modèle de conception comportemental qui permet de mettre en place un mécanisme de notification automatique entre objets. Il est utilisé lorsque plusieurs objets doivent réagir aux changements d'un objet central sans être directement couplés à lui. Composants principaux : Une Interface Observer et ses implémentations, une Classe Sujet qui gère la liste des observateurs et les notifie lorsqu'un changement survient.
Le **design pattern Observer** est utilisé pour créer une relation **un-à-plusieurs**, où un objet (**sujet**) informe d'autres objets (**observateurs**) de ses changements d'état. Voici une **implémentation en Java** :

### 🔹 **Étapes de l'implémentation**

1️⃣ Définir une **interface Observer** pour les classes qui souhaitent écouter les changements.
2️⃣ Créer une **classe Subject** qui maintient une liste d'observateurs et les notifie.
3️⃣ Implémenter des **classes concrètes** qui réagissent aux mises à jour.

### 🔹 **Exemple en Java**

```java
import java.util.ArrayList;
import java.util.List;

// Interface Observer
interface Observer {
    void update(String message);
}

// Classe Subject (Observable)
class Subject {
    private List<Observer> observers = new ArrayList<>();

    void addObserver(Observer observer) {
        observers.add(observer);
    }

    void removeObserver(Observer observer) {
        observers.remove(observer);
    }

    void notifyObservers(String message) {
        for (Observer observer : observers) {
            observer.update(message);
        }
    }
}

// Classe concrète Observer
class ConcreteObserver implements Observer {
    private String name;

    ConcreteObserver(String name) {
        this.name = name;
    }

    @Override
    public void update(String message) {
        System.out.println(name + "" a reçu la mise à jour : "" + message);
    }
}

// Test du pattern Observer
public class ObserverPatternDemo {
    public static void main(String[] args) {
        Subject subject = new Subject();

        Observer observer1 = new ConcreteObserver(""Observer 1"");
        Observer observer2 = new ConcreteObserver(""Observer 2"");

        subject.addObserver(observer1);
        subject.addObserver(observer2);

        subject.notifyObservers(""Nouvelle notification !"");
    }
}
```

### 🔹 **Explication**

✅ `Observer` définit une méthode `update()` pour réagir aux changements.
✅ `Subject` gère une liste d'observateurs et les notifie via `notifyObservers()`.
✅ `ConcreteObserver` implémente `Observer` et affiche les mises à jour reçues.

📌 **Cas d'utilisation** : Ce pattern est couramment utilisé dans les **interfaces graphiques**, les **systèmes de notifications** et les **flux de données**.

## ✅ Proxy

Composant intermédiaire entre un client et un serveur, utilisé pour filtrer, sécuriser ou mettre en cache les requêtes. Objectif : Offrir une interface identique à celle de l'objet réel tout en ajoutant des fonctionnalités supplémentaires.

- Contrôle d'accès → Limite l'accès à certaines opérations sensibles.
- Optimisation → Permet un chargement différé (Lazy Loading).
- Sécurité → Ajoute des vérifications avant d'exécuter une action.
- Gestion des ressources → Peut réduire les appels réseau ou base de données.

## ✅  Singleton

Design pattern de création qui garantit qu’une classe ne possède qu’une seule instance et fournit un point d’accès global à cette instance.
Exemple de code :

```
class Singleton {
    private static Singleton instance;

    // Constructeur privé pour empêcher l'instanciation directe
    private Singleton() {}

    // Méthode d'accès à l'instance (Lazy Initialization)
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }

    public void afficherMessage() {
        System.out.println(""Instance unique du Singleton !"");
    }
}
```

[⬅️ Retour à l'accueil](../index.md)
