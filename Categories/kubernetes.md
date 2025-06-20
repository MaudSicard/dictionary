# 🟦 Catégorie : Kubernetes

<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Recherche dans la page</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"></script>
  <style>
    /* Optionnel : style pour mettre en évidence les résultats */
    mark {
      background: yellow;
      padding: 0;
    }
  </style>
</head>
<body>
  <input type="text" id="search" placeholder="Rechercher dans la page..." />

  <div id="content">
    <p>Voici un exemple de texte long. Vous pouvez ajouter autant de paragraphes que nécessaire. La recherche vous aidera à retrouver rapidement des informations spécifiques directement dans cette page.</p>
    <p>Chaque fois que vous tapez dans la barre, le terme recherché sera mis en surbrillance.</p>
  </div>
  <script>
    const context = document.querySelector("#content");
    const markInstance = new Mark(context);
    document.getElementById("search").addEventListener("input", function() {
      const keyword = this.value;
      markInstance.unmark({
        done: function() {
          if (keyword) {
            markInstance.mark(keyword);
          }
        }
      });
    });
  </script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"></script>

</body>
</html>

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

[⬅️ Retour à l'accueil](../index.md)
