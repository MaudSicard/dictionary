# 🟦 Catégorie : DevOps


## ✅ Architecture distribuée
> Système informatique dont les composants sont répartis sur plusieurs machines, souvent interconnectées par un réseau, pour améliorer la résilience, la scalabilité et la performance.
## ✅ Chaos Engineering
> Pratique qui consiste à tester la résilience des systèmes en introduisant des pannes contrôlées pour observer et corriger les défaillances.
## ✅ CI / CD
> Intégration Continue (CI) et Déploiement Continu (CD) : pratiques DevOps qui automatisent le test, l'intégration et le déploiement d'applications.
## ✅ Cloud
> Ensemble de services informatiques (stockage, calcul, bases de données, etc.) accessibles à distance via Internet, souvent facturés à l’usage.
## ✅ Cloud Native
> Le **développement cloud natif** repose sur une approche moderne de conception d’applications optimisées pour le cloud. Il permet de créer des systèmes **scalables**, **résilients** et **flexibles**, en exploitant pleinement les services des **cloud providers** comme **AWS**, **Azure** et **GCP**.

### 🔹 **Principes du développement cloud natif**
✅ **Microservices** : Les applications sont décomposées en services indépendants, facilitant la maintenance et l’évolution.
✅ **Conteneurs** : Utilisation de **Docker** et **Kubernetes** pour déployer des applications de manière portable et efficace.
✅ **Infrastructure as Code (IaC)** : Automatisation du déploiement avec des outils comme **Terraform**, **CloudFormation** ou **Bicep**.
✅ **Observabilité** : Monitoring avancé avec **Prometheus**, **Grafana**, **Datadog** et **OpenTelemetry**.
✅ **Serverless** : Exécution de code sans gestion de serveurs avec **AWS Lambda**, **Azure Functions** ou **Google Cloud Functions**.

### 🔹 **Comparaison des cloud providers**
| Critère | AWS | Azure | GCP |
|---------|-----|------|-----|
| **Part de marché** | Leader (34%) | 2e (21%) | 3e (11%) |
| **Stockage** | S3 (standard du marché) | Azure Blob Storage | Google Cloud Storage |
| **Bases de données** | RDS, DynamoDB | Cosmos DB, SQL Server | BigQuery, Firestore |
| **Compute** | EC2, Lambda | Virtual Machines, Functions | Compute Engine, Cloud Run |
| **IA & Machine Learning** | SageMaker | Azure AI | Vertex AI, AutoML |
| **Sécurité** | IAM, KMS | Active Directory, Sentinel | IAM, Security Command Center |

### 🔹 **Pourquoi choisir un cloud provider ?**
✅ **AWS** : Idéal pour les grandes entreprises et les architectures complexes.
✅ **Azure** : Parfait pour les entreprises utilisant l’écosystème Microsoft.
✅ **GCP** : Excellente option pour l’analyse de données et l’IA.

## ✅ CPU
> Unité centrale de traitement ; composant matériel qui exécute les instructions d’un programme informatique.
## ✅ Crossplane
> Crossplane est un framework open-source qui étend Kubernetes pour gérer des ressources externes comme des bases de données, des services cloud et des infrastructures. Il permet aux équipes de créer des APIs personnalisées et d'automatiser le provisionnement des ressources via des manifests Kubernetes.
## ✅ DevOps
> Culture et ensemble de pratiques visant à unifier le développement logiciel (Dev) et l’exploitation informatique (Ops) pour livrer plus rapidement et de manière fiable.
## ✅ DevSecOps
> Extension de DevOps intégrant la sécurité dès les premières étapes du cycle de développement, plutôt que comme une phase séparée.
## ✅ Espace disque
> Capacité de stockage disponible sur un disque dur ou SSD utilisée pour stocker fichiers, bases de données, logs, etc.
## ✅ GPU
> Un GPU (Graphics Processing Unit) est un processeur spécialisé conçu pour effectuer des calculs graphiques et parallèles à grande vitesse. Il est principalement utilisé pour le rendu d'images, mais ses capacités de calcul lui permettent aussi d'être exploité dans des domaines comme l'intelligence artificielle et le minage de cryptomonnaies
## ✅ GPU et CPU
> Le GPU est une unité de traitement graphique qui fonctionne en parallèle avec le CPU (Central Processing Unit). Contrairement au CPU, qui exécute des tâches de manière séquentielle, le GPU est optimisé pour traiter simultanément un grand nombre de calculs, ce qui le rend idéal pour les applications nécessitant une grande puissance de calcul
## ✅  Infrastructure as Code (IaC)
> Pratique qui consiste à gérer l’infrastructure (réseaux, machines, services) via du code (ex : Terraform, Ansible), versionnable et automatisable.
## ✅  Lazy et eager loading
> Techniques de chargement de données : lazy (à la demande, plus performant) vs eager (chargement immédiat, plus simple mais coûteux).
## ✅  Monitoring
> Ensemble de pratiques et d’outils permettant de surveiller l’état, la performance et la santé d’une application ou infrastructure en temps réel.

## ✅ Bonnes pratiques de monitoring
> Le **monitoring** d’une application est essentiel pour détecter les problèmes, optimiser les performances et assurer une haute disponibilité. Voici les **bonnes pratiques** pour un monitoring efficace :

### 🔹 **1. Définir des objectifs clairs**
Avant de mettre en place un monitoring, pose-toi les bonnes questions :
✅ Quels sont les indicateurs critiques pour ton application ? (CPU, mémoire, latence…)
✅ Quels seuils déclenchent une alerte ? (ex. : temps de réponse > 500ms)
✅ Qui doit être alerté en cas de problème ? (DevOps, SRE, équipe produit…)

---

### 🔹 **2. Mettre en place un monitoring **Multi-couches**
Une bonne stratégie inclut plusieurs niveaux :
✅ **Infrastructure** : CPU, RAM, stockage, latence réseau
✅ **Application** : Erreurs, logs, traces distribuées
✅ **Services tiers** : API externes, bases de données, files de messages
✅ **Expérience utilisateur** : Temps de chargement, disponibilité

---

### 🔹 **3. Utiliser des outils adaptés**
Parmi les solutions populaires :
✅ **Prometheus + Grafana** → Monitoring et visualisation avancée
✅ **Datadog** → Observabilité complète (logs, métriques, traces)
✅ **OpenTelemetry** → Standardisation de la collecte de données
✅ **Jaeger ou Zipkin** → Tracing distribué pour analyser les appels API
✅ **ELK Stack (Elasticsearch, Logstash, Kibana)** → Centralisation des logs

---

### 🔹 **4. Intégrer le monitoring dès le développement**
Ajoute des **métriques** et **traces** dès l’écriture du code :
```java
import io.micrometer.core.instrument.MeterRegistry;
import jakarta.inject.Inject;

public class MonitoringService {
    @Inject
    MeterRegistry registry;

    public void trackRequest() {
        registry.counter(""requests.count"").increment();
    }
}
```

---

### 🔹 **5. Automatiser les alertes et remontées d’incidents**
✅ **Définis des seuils critiques** (`CPU > 80%`, `latence > 500ms`)
✅ **Utilise des webhooks ou Slack pour les notifications**
✅ **Active des dashboards en temps réel** pour suivre les tendances
✅ **Corrige automatiquement certains incidents** (auto-scaling, restart de services)

---

### 🔹 **6. Tester régulièrement le monitoring**
Un monitoring efficace doit être testé régulièrement :
✅ Simule des pannes (`kill -9 <process>`, `iptables drop`)
✅ Vérifie la réactivité des alertes (`uptime-check`, `end-to-end monitoring`)
✅ Analyse les logs et traces distribuées (`opentelemetry span analysis`)

---

### 🔹 **Résumé**
✅ **Définir des métriques et objectifs clairs**
✅ **Utiliser des outils modernes comme Prometheus, Datadog ou OpenTelemetry**
✅ **Automatiser les alertes et remontées d’incidents**
✅ **Tester régulièrement pour valider la fiabilité du monitoring**

## ✅ Nginx
> Serveur web performant, aussi utilisé comme proxy inverse, load balancer, ou cache HTTP dans les architectures modernes.
## ✅ Observabilité
> Capacité d’un système à fournir des informations claires sur son état interne à travers des logs, métriques et traces.

## ✅ Bonnes pratiques d'observabilité
> L'**observabilité** est essentielle pour comprendre l'état interne d'un système à partir de ses sorties externes. Elle va au-delà du simple **monitoring** en permettant une analyse proactive des performances et des incidents. Voici quelques **bonnes pratiques** pour une observabilité efficace :

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

## ✅ Semantic Release
> Semantic Release est un outil qui automatise la gestion des versions et des publications en fonction des messages de commit. Il est souvent utilisé avec GitLab pour générer des releases, des notes de version et publier des artefacts.

## ✅ Tracing distribué
> Suivi des requêtes à travers plusieurs services dans un système distribué pour diagnostiquer les problèmes de performance.


[⬅️ Retour à l'accueil](../index.md)