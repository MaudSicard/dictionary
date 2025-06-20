# 🟦 Catégorie : Docker

<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Recherche dans la page</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"></script>
  <style>
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

## ✅ Docker

Docker est une plateforme open source qui permet de développer, expédier et exécuter des applications dans des conteneurs.

## ✅ Docker API

Interface RESTful permettant de contrôler le moteur Docker (Docker Engine) à distance via des requêtes HTTP.

## ✅ Docker

CLI Interface en ligne de commande (docker) pour interagir avec le moteur Docker : créer, exécuter, inspecter des conteneurs.

## ✅ Docker Compose

Outil permettant de définir et de gérer des applications multi-conteneurs à l’aide d’un fichier YAML (docker-compose.yml).

## ✅ Docker engine

Moteur principal de Docker qui permet la création, l’exécution et la gestion des conteneurs.

## ✅ Docker Images

Modèle figé (read-only) contenant tout le nécessaire pour exécuter une application (code, bibliothèques, dépendances).

## ✅ Docker Swarm

Outil natif d’orchestration de conteneurs Docker permettant de gérer des clusters et le déploiement d’applications en mode distribué.

## ✅ Dockerfile

Fichier de configuration texte qui contient les instructions pour construire une image Docker personnalisée.

## ✅ Registry

Référentiel (public ou privé) où les images Docker sont stockées et partagées (ex : Docker Hub).

[⬅️ Retour à l'accueil](../index.md)
