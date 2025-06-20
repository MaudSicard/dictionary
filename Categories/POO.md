# 🟦 Catégorie : POO - Programmation Orientée Objet

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

## ✅ Classe

Élément fondamental en POO définissant les propriétés (attributs) et comportements (méthodes) d’un objet.

## ✅ Classe abstraite

Classe qui ne peut pas être instanciée directement, servant de modèle à d'autres classes via l’héritage. Elle peut contenir des méthodes abstraites (non implémentées).

## ✅ DRY

(Don't Repeat Yourself) Principe de développement visant à éviter la duplication de code en factorisant les logiques répétées dans des fonctions ou modules réutilisables.

## ✅ Encapsulation

L'encapsulation est l'un des principes fondamentaux de la programmation orientée objet (POO). Elle vise à protéger les données d'un objet en restreignant l'accès direct à ses attributs et en obligeant leur manipulation via des méthodes dédiées. L'encapsulation repose sur trois concepts clés : 1️⃣ Déclaration des attributs en private pour empêcher leur accès direct. 2️⃣ Utilisation de getters et setters pour permettre un accès contrôlé. 3️⃣ Définition de règles métiers dans les méthodes pour valider les modifications.

## ✅ Héritage

Mécanisme en POO où une classe (enfant) hérite des propriétés et méthodes d’une autre classe (parent), facilitant la réutilisation du code.

## ✅ Injection de dépendances

Technique où les dépendances d’un objet (services, configurations...) sont fournies de l’extérieur, facilitant testabilité et modularité.

## ✅ Interface

Contrat en POO qui définit un ensemble de méthodes sans implémentation, que les classes concrètes doivent respecter.

## ✅ Inversion de contrôle (IoC)

Inversion de contrôle (IoC) est un principe de conception en programmation où le flux de contrôle du programme est inversé : au lieu que l’application appelle explicitement des composants, c’est un cadre (framework) ou un conteneur qui gère ces appels et fournit les dépendances.

## ✅ Objet

Instance concrète d’une classe en programmation orientée objet, possédant ses propres données (attributs) et comportements (méthodes).

## ✅ Polymorphisme

Le polymorphisme est un concept fondamental de la programmation orientée objet (POO) qui permet à un même code d’être utilisé avec différents types d’objets. Il améliore la flexibilité, la réutilisation du code et la facilité de maintenance. ex : Polymorphisme de sous-type (ou d’inclusion), Polymorphisme paramétrique (ou générique), Polymorphisme ad hoc (ou surcharge).

## ✅ POO (Programmation Orientée Objet)

Paradigme de programmation basé sur les objets, la classe, l’héritage, l’encapsulation et le polymorphisme.

## ✅ SOLID

Acronyme représentant cinq principes de conception en POO : Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion.

</div>
[⬅️ Retour à l'accueil](../index.md)