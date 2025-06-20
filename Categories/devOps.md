# 🟦 Catégorie : DevOps

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

## ✅ Architecture distribuée

Système informatique dont les composants sont répartis sur plusieurs machines, souvent interconnectées par un réseau, pour améliorer la résilience, la scalabilité et la performance.

## ✅ Bonnes pratiques de monitoring

Le **monitoring** d’une application est essentiel pour détecter les problèmes, optimiser les performances et assurer une haute disponibilité. Voici les **bonnes pratiques** pour un monitoring efficace :

### 🔹 **1. Définir des objectifs clairs**

Avant de mettre en place un monitoring, pose-toi les bonnes questions :
✅ Quels sont les indicateurs critiques pour ton application ? (CPU, mémoire, latence…)
✅ Quels seuils déclenchent une alerte ? (ex. : temps de réponse > 500ms)
✅ Qui doit être alerté en cas de problème ? (DevOps, SRE, équipe produit…)

### 🔹 **2. Mettre en place un monitoring Multi-couches**

Une bonne stratégie inclut plusieurs niveaux :
✅ **Infrastructure** : CPU, RAM, stockage, latence réseau
✅ **Application** : Erreurs, logs, traces distribuées
✅ **Services tiers** : API externes, bases de données, files de messages
✅ **Expérience utilisateur** : Temps de chargement, disponibilité

### 🔹 **3. Utiliser des outils adaptés**

Parmi les solutions populaires :
✅ **Prometheus + Grafana** → Monitoring et visualisation avancée
✅ **Datadog** → Observabilité complète (logs, métriques, traces)
✅ **OpenTelemetry** → Standardisation de la collecte de données
✅ **Jaeger ou Zipkin** → Tracing distribué pour analyser les appels API
✅ **ELK Stack (Elasticsearch, Logstash, Kibana)** → Centralisation des logs

### 🔹 **4. Intégrer le monitoring dès le développement**

Ajoute des **métriques** et **traces** dès l’écriture du code :

```java
import io.micrometer.core.instrument.MeterRegistry;
import jakarta.inject.Inject;

public class MonitoringService {
    @Inject
    MeterRegistry registry;

    public void trackRequest() {
        registry.counter("requests.count").increment();
    }
}
```

### 🔹 **5. Automatiser les alertes et remontées d’incidents**

✅ **Définis des seuils critiques** (`CPU > 80%`, `latence > 500ms`)
✅ **Utilise des webhooks ou Slack pour les notifications**
✅ **Active des dashboards en temps réel** pour suivre les tendances
✅ **Corrige automatiquement certains incidents** (auto-scaling, restart de services)

### 🔹 **6. Tester régulièrement le monitoring**

Un monitoring efficace doit être testé régulièrement :
✅ Simule des pannes (`kill -9 <process>`, `iptables drop`)
✅ Vérifie la réactivité des alertes (`uptime-check`, `end-to-end monitoring`)
✅ Analyse les logs et traces distribuées (`opentelemetry span analysis`)

### 🔹 **Résumé**

✅ **Définir des métriques et objectifs clairs**
✅ **Utiliser des outils modernes comme Prometheus, Datadog ou OpenTelemetry**
✅ **Automatiser les alertes et remontées d’incidents**
✅ **Tester régulièrement pour valider la fiabilité du monitoring**

## ✅ Bonnes pratiques d'observabilité

L'**observabilité** est essentielle pour comprendre l'état interne d'un système à partir de ses sorties externes. Elle va au-delà du simple **monitoring** en permettant une analyse proactive des performances et des incidents. Voici quelques **bonnes pratiques** pour une observabilité efficace :

### 🔹 **1. Adopter les trois piliers de l'observabilité**

L'observabilité repose sur trois éléments clés :
✅ **Logs** : Capturent les événements du système pour une analyse détaillée.
✅ **Métriques** : Données quantitatives sur les performances (CPU, latence, erreurs…).
✅ **Traces** : Suivi des requêtes à travers les services pour identifier les goulots d'étranglement.

### 🔹 **2. Intégrer l'observabilité dès la conception**

✅ **Définir des KPIs clairs** pour mesurer la santé du système.
✅ **Standardiser les formats de logs et métriques** pour faciliter l'analyse.
✅ **Automatiser la collecte et l'analyse des données** avec des outils comme **Prometheus**, **Datadog** ou **OpenTelemetry**.

### 🔹 **3. Corréler les données pour une vision globale**

✅ **Éviter la supervision en silos** : Relier logs, métriques et traces pour une vue unifiée.
✅ **Utiliser des dashboards dynamiques** pour visualiser les tendances et anomalies.
✅ **Mettre en place des alertes intelligentes** basées sur des seuils et des tendances.

### 🔹 **4. Automatiser la détection et la résolution des incidents**

✅ **Déployer des outils d'auto-remédiation** pour corriger automatiquement certains problèmes.
✅ **Analyser les causes profondes** plutôt que de traiter uniquement les symptômes.
✅ **Utiliser l'IA et le machine learning** pour anticiper les dégradations de performance.

### 🔹 **5. Tester et améliorer continuellement**

✅ **Effectuer des tests de charge et de résilience** pour valider la robustesse du système.
✅ **Simuler des pannes** pour vérifier la réactivité des alertes et des équipes.
✅ **Adapter les stratégies d'observabilité** en fonction des évolutions du système.

## ✅ Chaos Engineering

Pratique qui consiste à tester la résilience des systèmes en introduisant des pannes contrôlées pour observer et corriger les défaillances.

## ✅ CI / CD

Intégration Continue (CI) et Déploiement Continu (CD) : pratiques DevOps qui automatisent le test, l'intégration et le déploiement d'applications.

## ✅ Cloud

Ensemble de services informatiques (stockage, calcul, bases de données, etc.) accessibles à distance via Internet, souvent facturés à l’usage.

## ✅ Cloud Native

Le **développement cloud natif** repose sur une approche moderne de conception d’applications optimisées pour le cloud. Il permet de créer des systèmes **scalables**, **résilients** et **flexibles**, en exploitant pleinement les services des **cloud providers** comme **AWS**, **Azure** et **GCP**.

### 🔹 **Principes du développement cloud natif**

✅ **Microservices**
✅ **Conteneurs**
✅ **Infrastructure as Code (IaC)**
✅ **Observabilité**
✅ **Serverless**

### 🔹 **Comparaison des cloud providers**

| Critère              | AWS           | Azure                 | GCP                       |
| -------------------- | ------------- | --------------------- | ------------------------- |
| **Part de marché**   | Leader (34%)  | 2e (21%)              | 3e (11%)                  |
| **Stockage**         | S3            | Azure Blob Storage    | Google Cloud Storage      |
| **Bases de données** | RDS, DynamoDB | Cosmos DB, SQL Server | BigQuery, Firestore       |
| **Compute**          | EC2, Lambda   | Virtual Machines      | Compute Engine, Cloud Run |
| **IA & ML**          | SageMaker     | Azure AI              | Vertex AI, AutoML         |
| **Sécurité**         | IAM, KMS      | Active Directory      | IAM, Security Cmd Center  |

### 🔹 **Pourquoi choisir un cloud provider ?**

✅ **AWS** – Idéal pour grandes entreprises
✅ **Azure** – Idéal pour les écosystèmes Microsoft
✅ **GCP** – Fort sur l’analytique et l’IA

## ✅ CPU

Unité centrale de traitement ; composant matériel qui exécute les instructions d’un programme informatique.

## ✅ Crossplane

Framework open-source étendant Kubernetes pour gérer des ressources externes. Permet la création d’APIs personnalisées et le provisionnement automatisé.

## ✅ DevOps

Culture et ensemble de pratiques visant à unifier le développement logiciel (Dev) et l’exploitation informatique (Ops) pour livrer plus rapidement et de manière fiable.

## ✅ DevSecOps

Extension de DevOps intégrant la sécurité dès les premières étapes du cycle de développement.

## ✅ Espace disque

Capacité de stockage disponible sur un disque dur ou SSD utilisée pour stocker fichiers, bases de données, logs, etc.

## ✅ GPU

Un GPU (Graphics Processing Unit) est un processeur spécialisé conçu pour effectuer des calculs graphiques et parallèles à grande vitesse.

## ✅ GPU et CPU

Le GPU fonctionne en parallèle avec le CPU. Il est optimisé pour traiter simultanément un grand nombre de calculs, idéal pour les charges lourdes.

## ✅ Infrastructure as Code (IaC)

Pratique qui consiste à gérer l’infrastructure via du code (Terraform, Ansible…), versionnable et automatisable.

## ✅ Lazy et eager loading

Techniques de chargement de données : lazy (à la demande) vs eager (chargement immédiat).

## ✅ Monitoring

Ensemble de pratiques et d’outils permettant de surveiller l’état, la performance et la santé d’une application ou infrastructure.

## ✅ Nginx

Serveur web performant, aussi utilisé comme proxy inverse, load balancer, ou cache HTTP.

## ✅ Observabilité

Capacité d’un système à fournir des informations claires sur son état interne à travers des logs, métriques et traces.

## ✅ Semantic Release

Outil qui automatise la gestion des versions et des publications selon les messages de commit.

## ✅ Tracing distribué

Suivi des requêtes à travers plusieurs services dans un système distribué pour diagnostiquer les problèmes de performance.

</div>
[⬅️ Retour à l'accueil](../index.md)
