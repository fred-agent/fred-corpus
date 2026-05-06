# FICHE RÉFÉRENCE PROJET — THALES SERVICES NUMÉRIQUES

**Référence interne :** TSN-DSP-REF-2023-047
**Business Line :** Systèmes d'Information de Sécurité Critiques
**Business Unit :** Défense et Secteur Public
**Statut :** Projet clôturé — réversibilité effectuée en 2024

---

## 1. Identification du projet

| Champ | Valeur |
|---|---|
| **Titre** | Refonte et industrialisation de l'Entrepôt de Données de Santé (EDS) — CHU de Montargon |
| **Code projet** | EDS-MONT-2021 |
| **Client** | Centre Hospitalier Universitaire de Montargon (CHU-M) |
| **Commanditaire** | Direction des Systèmes d'Information — Département Innovation & Données |
| **Période de réalisation** | Mars 2021 — Janvier 2024 (34 mois) |
| **Montant global** | 4,8 M€ HT (tranches fermes + conditionnelles) |
| **Modèle contractuel** | Accord-cadre à bons de commande — mix BPU (unités d'œuvre) et forfait (tranches projet) |
| **Type de procédure** | Appel d'offres ouvert formalisé (> seuils UE) |

---

## 2. Contexte client

Le CHU de Montargon est un établissement public de santé de 6 200 lits, couvrant 1,8 million de patients par an. Sa DSI (180 ETP, 22 M€ d'investissement annuel) portait depuis 2018 un entrepôt de données de santé (EDS) initialement construit sur une stack Hadoop/HDFS vieillissante, peu scalable et coûteuse en exploitation.

Les enjeux exprimés au démarrage :
- Migration de la plateforme vers une architecture cloud-native on-premise (Kubernetes + stockage objet)
- Industrialisation de l'ingestion des données cliniques (DPI Orbis, biologie, imagerie DICOM)
- Mise en qualité et standardisation FHIR/OMOP pour supporter les projets de recherche clinique
- Conformité RGPD / HDS renforcée (traçabilité, anonymisation, gouvernance des accès)
- Réduction du TCO de 30 % sur 3 ans

---

## 3. Périmètre et prestations réalisées

Thales Services Numériques est intervenu comme titulaire unique sur un accord-cadre à quatre lots, avec une équipe allant jusqu'à 18 intervenants au pic d'activité.

### Lot infrastructure données
- Migration HDFS → MinIO (S3-compatible) + Delta Lake sur cluster Kubernetes 14 nœuds
- Mise en place cluster de calcul GPU (12 Nvidia A100) pour charges NLP et imagerie
- Industrialisation IaC (Terraform, Ansible) et supervision Prometheus/Grafana
- Durcissement sécurité (Vault, OpenID Connect, revues de logs centralisées)

### Lot ingénierie des données
- Pipelines ELT Spark/Python pour 11 sources cliniques (DPI, laboratoires, PACS imagerie, pharmacie)
- Connecteurs CDC temps réel via Debezium + Kafka
- Modélisation FHIR R4 + mapping OMOP CDM v5.4 pour cohortes de recherche
- Outillage qualité de données (Great Expectations + dashboards Superset)

### Lot science des données
- Développement de 3 modèles ML en production :
  - NLP d'extraction d'entités sur comptes-rendus d'hospitalisation (spaCy + modèle transformer fine-tuné)
  - Prédiction de réadmission à 30 jours (gradient boosting, MLflow)
  - Segmentation d'images radiologiques (PyTorch, déploiement via Triton Inference Server)
- Pipeline MLOps complet (train → eval → deploy → monitoring avec Evidently)

### Lot accompagnement
- Support niveau 2 aux équipes de recherche (12 projets cliniques accompagnés)
- Formation de 45 praticiens et internes à l'usage des DataLabs Jupyter
- Documentation d'exploitation (DAT, DEX) pour l'ensemble des composants
- Assistance à la coordination de projets (PMO) sur le portefeuille recherche du CHU-M

---

## 4. Stack technique

- **Orchestration :** Kubernetes (Rancher), Argo Workflows, Airflow
- **Stockage :** MinIO (S3), Delta Lake, PostgreSQL, Elasticsearch, MongoDB
- **Traitement :** Apache Spark, Kafka, Debezium, Python, Scala
- **ML / Data Science :** PyTorch, spaCy, MLflow, Triton Inference Server, JupyterHub
- **Observabilité :** Prometheus, Grafana, Loki, OpenTelemetry
- **Sécurité :** HashiCorp Vault, Keycloak (OIDC), SonarQube, Trivy
- **CI/CD :** GitLab CI, ArgoCD
- **BI :** Apache Superset, Metabase

---

## 5. Organisation et pilotage

- **Équipe Thales :** 1 Directeur de projet, 1 Architecte Big Data, 1 Responsable sécurité, 14 ingénieurs (data eng, data science, DevOps), 1 PMO
- **Gouvernance :** comité opérationnel mensuel, COPIL trimestriel, revue annuelle avec la DSI et la direction médicale
- **Méthode :** Scrum adapté (sprints 3 semaines), avec backlog partagé sur Jira / Confluence
- **Réversibilité :** dossier de réversibilité produit 6 mois avant la fin du marché, transfert de compétences sur 4 mois vers les équipes internes du CHU-M

---

## 6. Résultats et bénéfices mesurés

| Indicateur | Avant projet | Après projet | Delta |
|---|---|---|---|
| Temps moyen d'ingestion d'une nouvelle source | 6 semaines | 9 jours | -78 % |
| Disponibilité plateforme MCO | 97,2 % | 99,7 % | +2,5 pts |
| Nombre de projets de recherche supportés | 9 | 23 | +155 % |
| Coût d'exploitation annuel | 1,4 M€ | 0,95 M€ | -32 % |
| Délai moyen d'accès à une cohorte anonymisée | 3 semaines | 4 jours | -81 % |
| Taux de livrables acceptés sans réserve | 82 % | 94 % | +12 pts |

**Reconnaissance externe :** projet présenté aux Journées Francophones d'Informatique Médicale 2023, prix « Innovation Entrepôt de Données » décerné par l'APSSIS en 2023.

---

## 7. Points forts différenciants

- **Expertise FHIR/OMOP de bout en bout** : Thales a capitalisé sur un centre de compétence dédié à la standardisation des données de santé, permettant d'accélérer la mise en qualité de 40 % par rapport aux estimations initiales.
- **Approche "Platform as a Product"** : la plateforme a été conçue comme un produit interne avec roadmap trimestrielle et feedback utilisateur, ce qui a fortement contribué à l'adoption par les cliniciens-chercheurs.
- **Sécurité by design** : architecture validée par l'ANSSI et conforme au référentiel HDS, audit de sécurité externe passé sans non-conformité majeure.
- **Continuité humaine** : le Directeur de projet et l'Architecte Big Data ont été maintenus sur l'ensemble des 34 mois du projet — un facteur clé de confiance souligné par le client lors de la revue finale.

---

## 8. Difficultés rencontrées et enseignements

- **Migration HDFS → S3 sous-estimée initialement** (+2 mois) en raison de la volumétrie d'imagerie DICOM (420 To). Enseignement : intégrer systématiquement un audit de volumétrie fine avant le chiffrage.
- **Conduite du changement auprès des chercheurs** : adoption plus lente qu'anticipé sur JupyterHub, corrigée par la mise en place d'un programme de formation et d'un canal de support Mattermost dédié.
- **Coordination avec l'éditeur du DPI Orbis** : nécessité d'intégrer un prestataire tiers dans le plan projet — à prévoir systématiquement dans les futurs EDS.

---

## 9. Contact interne Thales

- **Directeur de projet :** [ANONYMISÉ] — disponible pour partage d'expérience
- **Architecte référent :** [ANONYMISÉ]
- **Centre de compétence concerné :** CoC Data Platforms Santé — Thales Services Numériques

---

*Fiche rédigée dans le cadre du partage de références pour les opportunités commerciales de la BL SISC. Diffusion restreinte équipe Bid Management.*
