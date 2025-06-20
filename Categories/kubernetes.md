# 🟦 Catégorie : Kubernetes

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

<!-- Content in which to search -->
<div id="content" markdown="1">

## ✅ Cluster

Groupe de machines (physiques ou virtuelles) agissant comme une seule entité pour héberger des applications ou services de manière résiliente.

## ✅ Container

Unité légère et portable qui contient une application, ses dépendances et sa configuration, isolée de l’environnement d’exécution hôte (ex : Docker).

## ✅ Ingress

Composant Kubernetes permettant de gérer l’accès HTTP(S) externe aux services via un contrôleur (ex. Nginx Ingress Controller).

## ✅ Kubernetes Plateforme

Open source d’orchestration de conteneurs, permettant de déployer, gérer et faire évoluer automatiquement des applications conteneurisées.

## ✅ Master nodes et worker nodes

Dans Kubernetes : les master nodes contrôlent et orchestrent le cluster, tandis que les worker nodes exécutent les conteneurs applicatifs.

## ✅ Orchestration de containers

Gestion automatique du déploiement, de la montée en charge, du réseau et de la disponibilité des conteneurs (ex : via Kubernetes).

## ✅ Pod

Plus petite unité déployable dans Kubernetes, contenant un ou plusieurs conteneurs partageant le même réseau et stockage.

## ✅ ReplicaSets

Contrôleur Kubernetes qui s'assure qu’un nombre défini de copies (réplicas) d’un pod sont en exécution à tout moment.

## ✅ Scalabilité

Capacité d’un système à supporter une augmentation de charge (utilisateurs, données, requêtes) en maintenant ses performances.

## ✅ Scheduler

Composant (ex. dans Kubernetes) chargé de planifier où et quand exécuter les pods en fonction des ressources disponibles.

## ✅ Sharding

Technique de partitionnement horizontal des données où une base est divisée en fragments (shards), chacun stocké sur un serveur différent pour améliorer la scalabilité.

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
