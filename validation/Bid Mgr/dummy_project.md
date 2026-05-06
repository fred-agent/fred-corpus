# CAHIER DES CLAUSES TECHNIQUES PARTICULIÈRES

**Consultation N° 25-12 IT**

**Objet :** Prestations d'Assistance Technique dans le domaine du traitement d'information et des entrepôts de données pour la Direction des Systèmes d'Information du CHU de Valdor.

Ce document est associé au Cahier des Clauses Administratives Particulières.

**CENTRE HOSPITALIER UNIVERSITAIRE DE VALDOR**
12, avenue des Sciences — 69500 VALDOR
Tél. : 04 72 XX XX XX

---

## SOMMAIRE

- ARTICLE 1. OBJET DU MARCHÉ
- ARTICLE 2. CONTEXTE SI ET ORGANISATIONNEL
- ARTICLE 3. ALLOTISSEMENT
- ARTICLE 4. LOT 1 – ASSISTANCE TECHNIQUE INFRASTRUCTURE DONNÉES
- ARTICLE 5. LOT 2 – INGÉNIERIE ET SCIENCE DES DONNÉES
- ARTICLE 6. LOT 3 – CONCEPTION D'OUTILS NUMÉRIQUES
- ARTICLE 7. LOT 4 – ACCOMPAGNEMENT UTILISATEURS ET PROJETS DE RECHERCHE
- ARTICLE 8. CONDITIONS D'EXÉCUTION ET SUIVI CONTRACTUEL
- ARTICLE 9. ANNEXES

---

## Article 1. Objet du marché

Le présent appel d'offres a pour objet la fourniture de prestations d'Assistance Technique dans le domaine du traitement de données de santé pour la Direction des Systèmes d'Information (DSI) du CHU de Valdor.

Les prestations décrites dans le cadre du présent marché s'appuient sur des unités d'œuvre (UO) décrites dans le présent CCTP et valorisées dans le cadre de la réponse financière du titulaire. Elles sont destinées à être commandées par le CHU de Valdor en fonction de ses besoins.

---

## Article 2. Contexte SI et contexte organisationnel

### Section 2.1. Présentation du CHU de Valdor

#### 2.1.1. Présentation générale

Le Centre Hospitalier Universitaire de Valdor (CHU-V) est un établissement public de santé assurant des missions de soins, d'enseignement, de recherche médicale, de prévention et d'éducation à la santé. Il constitue le centre hospitalier et universitaire de la métropole de Valdor.

Le CHU de Valdor dispose de :
- **8 500 lits** d'hospitalisation
- **650 places** en hôpital de jour
- **280 places** en hospitalisation à domicile (HAD)
- Chaque année, le CHU soigne plus de **2,5 millions de patients**

Le personnel du CHU de Valdor compte près de **18 000 agents** (22 % de personnel médical, 78 % de personnel non médical).

Les services médicaux sont organisés en **48 pôles** regroupant des services ou unités aux activités similaires ou complémentaires.

#### 2.1.2. Direction des Systèmes d'Information (DSI)

La Direction des Systèmes d'Information (DSI) a pour mission d'assister le Directeur Général dans la conception, le pilotage et la mise en œuvre de la politique du système d'information du CHU de Valdor.

Ses principales missions couvrent :
- La planification et le pilotage général des systèmes d'information
- La gestion du portefeuille des projets SI
- La maîtrise d'œuvre des projets informatiques
- La sécurité des systèmes d'information
- La gestion budgétaire et le contrôle de gestion informatiques

La DSI est composée de **220 professionnels** répartis en 8 pôles, avec un budget d'investissement de **28 M€** et un budget d'exploitation de **32 M€**.

### Section 2.2. Pôles fonctionnels de la DSI

La DSI du CHU de Valdor est organisée en pôles fonctionnels :

- **CAS** : Centre d'Applications et de Solutions
- **CIS** : Centre Infrastructures et Systèmes
- **IND** : Innovation & Données
- **OPS** : Opérations et Réseau
- **RC** : Relations Clients
- **RSSI** : Sécurité du SI
- **CSU** : Centre de Support Unifié

### Section 2.3. Département Innovation & Données (IND)

Le pôle Innovation & Données (IND) regroupe près de **60 collaborateurs** répartis en 5 domaines distincts. L'offre de services se structure autour de :

- **L'innovation numérique** : développement de services numériques pour les professionnels de santé et les patients, selon une approche produit agile.
- **L'entrepôt de données de santé du CHU-V (EDS-V)** : usage secondaire des données hospitalières (recherche, pilotage de l'activité). La plateforme supporte actuellement **plus de 15 projets de recherche**.
- **La bio-informatique** : plateforme d'analyse génomique pour les départements de biologie moléculaire du CHU-V.
- **La gestion de la donnée** : gouvernance, qualité et référentiels de données.

---

## Article 3. Allotissement de la consultation

La présente consultation comprend quatre lots :

| Désignation UO | Code | Lot 1 | Lot 2 | Lot 3 | Lot 4 |
|---|---|:---:|:---:|:---:|:---:|
| Spécification fonctionnelle générale | SFG | X | | | |
| Spécification fonctionnelle détaillée | SFD | X | | | |
| Support d'Exploitation | SUPEXP | X | | | |
| Infrastructures Données Massives | BIGINFRA | X | | | |
| Sécurité des Infrastructures | SECU | X | | | |
| Gestion de Projets DATA | PODATA | | X | | |
| Ingénierie des données | DATAENG | | X | | |
| Analyse des données | DATAANALYST | | X | | |
| Science des données | DATASCIENTIST | | X | | |
| Déploiement d'algorithmes | MLOPS | | X | | |
| Design UX/UI | DESIGNUXUI | | | X | |
| Design de Service | DESIGNSERV | | | X | |
| Recherche Utilisateur | RECHUX | | | X | |
| Design Graphique | DESIGNGRAPH | | | X | |
| Analyse et Mesure d'impact | IMPACT | | | X | |
| Management agile produit numérique | AGILENUM | | | X | |
| Gestion des projets de recherche | GESPJTR | | | | X |
| Assistance à la coordination de projets | PMO | | | | X |
| Support aux utilisateurs | SUPPTIL | | | | X |
| Réversibilité | REVERSD | X | X | X | X |

---

## Article 4. Lot 1 – Assistance Technique Infrastructure Données

### Contexte technique

La plateforme hébergeant l'Entrepôt de Données de Santé du CHU de Valdor comprend :

- Un cluster de stockage objet **S3 compatible** (migration depuis HDFS en cours)
- Un cluster d'applications **Kubernetes** pour les calculs via Spark
- Des machines **GPU** pour les calculs d'apprentissage automatique
- Des systèmes de gestion de base de données **PostgreSQL**, **Elasticsearch**, **Kafka**
- Des outils d'exploitation de données **JupyterLab** (noyaux R/Python)
- Des outils de **Business Intelligence** (Metabase, Apache Superset)
- Un moteur de stockage **Delta Lake** pour les données structurées

L'infrastructure on-premise au sein du data-center du CHU de Valdor compte :
- **12 machines** pour le cluster de calcul (1 800 Go RAM, 480 cores CPU, 600 To d'espace disque)
- **4 machines GPU** (16 GPU Nvidia A100)
- **8 machines CPU** dédiées aux environnements Jupyter

Un effort important est mené pour intégrer rapidement les données cliniques (structurées et non structurées) issues des systèmes d'information hospitaliers (DPI, logiciels de spécialité, imagerie, signaux physiologiques).

La plateforme contient les données médicales de **plus de 2 millions de patients** et supporte plus de 15 projets de recherche actifs.

### Section 4.1. Prestations attendues pour le lot 1

#### 4.1.1. SFG — Unité d'œuvre de Spécifications Fonctionnelles Générales

La prestation consiste à définir des Spécifications Fonctionnelles Générales et les formaliser dans un dossier en s'appuyant sur des rencontres avec des interlocuteurs désignés et/ou l'assimilation de documents existants.

**Contenu de la prestation :**
Pour un projet de développement, extension ou correction, le titulaire :
- Définit des SFG et les formalise dans un dossier
- Identifie les besoins métiers et leur priorité
- Décrit les fonctionnalités, données et règles de gestion
- Modélise le MCD général
- Précise les modalités de reprise de l'existant

**Livrables attendus :**
1. Dossier de spécifications fonctionnelles générales
2. Notes intermédiaires de reporting
3. Document de valorisation en UO
4. Restitution finale lors d'une réunion

**Métriques et niveaux de complexité :**

| Unité d'œuvre | Métrique | Complexité |
|---|---|---|
| SFG 1 | 1 procédure fonctionnelle | Faible — 1 validation intermédiaire |
| SFG 2 | 1 procédure fonctionnelle | Moyenne — 2 validations intermédiaires |
| SFG 3 | 1 procédure fonctionnelle | Grande — 3 validations intermédiaires |
| SFG 4 | 1 procédure fonctionnelle | Très grande — 4 validations intermédiaires |

#### 4.1.2. SFD — Unité d'œuvre de Spécifications Fonctionnelles Détaillées

La prestation consiste à définir des Spécifications Fonctionnelles Détaillées et les formaliser dans un dossier en s'appuyant sur des documents existants.

**Livrables attendus :**
1. Dossier de SFD (règles de gestion, MCD détaillé, maquettes d'écrans, interfaces)
2. Dossier de tests fonctionnels et de non-régression
3. Notes intermédiaires de reporting
4. Document de valorisation en UO

**Métriques et niveaux de complexité :**

| Unité d'œuvre | Complexité | Exigences métier |
|---|---|---|
| SFD 1 | Faible | Moins de 2 |
| SFD 2 | Moyenne | 3 à 5 |
| SFD 3 | Grande | 6 à 10 |
| SFD 4 | Très grande | 11 à 20 |

#### 4.1.3. BIGINFRA — Infrastructures de Données Massives

Cette prestation couvre :
- Mise en place d'infrastructures pour la gestion de données massives
- Administration et Maintenance en Conditions Opérationnelles (MCO)
- Supervision des infrastructures

**Activités principales :**
- Participation à la construction de plateformes Docker/Kubernetes
- Administration des clusters de calcul (GPU, CPU, NAS)
- Automatisation des tâches via Ansible
- Supervision avec Prometheus/Grafana
- Réalisation d'audits techniques périodiques
- Transfert de compétences vers les équipes du CHU-V

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| BIGINFRA 1.1 | Mise en place — composant standard | Faible |
| BIGINFRA 1.2 | Mise en place — composant spécifique + maquette | Moyenne |
| BIGINFRA 1.3 | Architecture d'orchestration + étude choix composants | Grande |
| BIGINFRA 2.1 | MCO — prise de connaissance + formation (8 pers.) | Faible |
| BIGINFRA 2.2 | MCO — administration mensuelle (forfait +/- 10%) | Moyenne |
| BIGINFRA 2.3 | MCO — audit ou expertise d'évolution | Grande |
| BIGINFRA 3.1 | Supervision — fonctionnalité standard | Faible |
| BIGINFRA 3.2 | Supervision — fonctionnalité spécifique | Moyenne |

#### 4.1.4. SUPEXP — Support à l'exploitation

**Activités :**
1. Prise de connaissance de l'application ou du module
2. Rédaction du Dossier d'Architecture Technique (DAT)
3. Rédaction du Dossier d'Exploitation (DEX)
4. Implémentation de l'architecture technique

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| SUPEXP 0.1 | Prise de connaissance — doc < 20 pages | Faible |
| SUPEXP 0.2 | Prise de connaissance — doc 21-50 pages | Moyenne |
| SUPEXP 0.3 | Prise de connaissance — doc 51-100 pages | Grande |
| SUPEXP 1.1 | DAT < 20 pages | Faible |
| SUPEXP 1.2 | DAT 21-50 pages | Moyenne |
| SUPEXP 1.3 | DAT 51-100 pages | Grande |
| SUPEXP 2.1 | DEX < 20 pages | Faible |
| SUPEXP 2.2 | DEX 21-50 pages | Moyenne |
| SUPEXP 2.3 | DEX 51-100 pages | Grande |
| SUPEXP 3.1 | Architecture non redondée sans PRA | Faible |
| SUPEXP 3.2 | Architecture non redondée avec PRA | Moyenne |
| SUPEXP 3.3 | Architecture haute disponibilité | Grande |

#### 4.1.5. SECU — Sécurité des Infrastructures

**Activités :**
- Audits sécurité et diagnostics de vulnérabilités
- Tests d'intrusion (pentest)
- Paramétrage et mise en œuvre de composants de sécurisation
- Développement de fonctionnalités de sécurisation spécifiques
- Transfert de compétences

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| SECU 1 | Paramétrage composant d'exploitation (revue comptes, logs) | Faible |
| SECU 2 | Mise en œuvre composant standard (OpenID, OAuth2, SonarQube) | Moyenne |
| SECU 3 | Développement spécifique + étude de choix de solution | Grande |

---

## Article 5. Lot 2 – Ingénierie et Science des Données

### Section 5.1. Contexte technique

Les données nécessaires aux traitements sont extraites des bases de données de production (DPI, logiciels de spécialité) et chargées dans un datalake via des pipelines ELT développés en Spark/Python et des connecteurs CDC (Debezium).

Les données sont transformées et mises en qualité (appariement multi-source, alignement terminologique, modélisation FHIR) dans une base Delta Lake sur un cluster de stockage S3.

Les données non structurées (documents texte, imagerie, signaux) sont traitées avec des algorithmes de machine learning développés en Python (PyTorch, spaCy).

Les données sont mises à disposition dans des espaces de travail sécurisés **DataLab** (JupyterLab, GPU Nvidia).

**Stack technique :**
- Front-end : ReactJS, NodeJS, tests automatisés (Playwright)
- Back-end : microservices REST, Elasticsearch, Python/Java, Kafka
- Bases de données : PostgreSQL, MongoDB, Redis
- DevOps : Git, Docker, Kubernetes, SonarQube, CI/CD GitLab

### Section 5.2. Prestations attendues pour le lot 2

#### 5.2.1. PODATA — Gestion de projets données

**Activités :**
- Cadrer et accompagner l'instruction d'un cas d'usage sur données
- Alimenter et prioriser le backlog de l'équipe
- Synchroniser et coordonner les différents métiers
- Superviser les étapes du delivery (livrables, tests)

**Profils :** Chef de Projet, Consultant

**Livrables :** Backlog priorisé, comptes-rendus de réunions, rapports de suivi

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| PODATA 1 | Conduite projet < 1 mois | Faible |
| PODATA 2 | Conduite projet 1-3 mois | Moyenne |
| PODATA 3 | Conduite projet > 3 mois | Grande |

#### 5.2.2. DATAENG — Ingénierie des données

**Activités :**
- Développement de pipelines ELT/ETL (Spark, Python, SQL)
- Intégration de sources de données hétérogènes
- Modélisation et standardisation des données (FHIR, OMOP)
- Mise en qualité des données

**Profils :** Data Engineer, Ingénieur Études et Développement

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| DATAENG 1 | Pipeline simple, source unique, transformations standards | Faible |
| DATAENG 2 | Pipeline multi-sources avec transformations métier | Moyenne |
| DATAENG 3 | Architecture complexe (streaming, CDC, standardisation) | Grande |

#### 5.2.3. DATAANALYST — Analyse des données

**Activités :**
- Exploration et analyse statistique de données de santé
- Création de tableaux de bord et rapports (Metabase, Superset)
- Formulation et vérification d'hypothèses métier

**Profils :** Data Analyst, Biostatisticien

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| DATAANALYST 1 | Analyse descriptive, données structurées | Faible |
| DATAANALYST 2 | Analyse multi-dimensionnelle, croisement sources | Moyenne |
| DATAANALYST 3 | Analyse longitudinale, cohortes complexes | Grande |

#### 5.2.4. DATASCIENTIST — Science des données

**Activités :**
- Développement de modules de visualisation de données complexes
- Modélisation prédictive et analytique
- Traitement du langage naturel (NLP) sur données médicales
- Traitement d'images médicales (Deep Learning)

**Profils :** Data Scientist, Ingénieur ML

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| DATASCIENTIST 1 | Visualisation standard, données structurées | Faible |
| DATASCIENTIST 2 | Modèle ML supervisé, données hétérogènes | Moyenne |
| DATASCIENTIST 3 | Deep Learning, données non structurées (texte/image) | Grande |

#### 5.2.5. MLOPS — Déploiement d'algorithmes

**Activités :**
- Mise en production de modèles de machine learning
- Automatisation des pipelines d'entraînement et d'évaluation
- Monitoring des modèles en production
- Gestion des versions de modèles (MLflow)

**Profils :** MLOps Engineer, DevOps

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| MLOPS 1 | Déploiement modèle batch, sans monitoring | Faible |
| MLOPS 2 | Déploiement API temps réel avec monitoring | Moyenne |
| MLOPS 3 | Pipeline ML complet (train/eval/deploy/monitor) | Grande |

---

## Article 6. Lot 3 – Conception et Réalisation d'Outils Numériques

### Section 6.1. Description des besoins

Le CHU de Valdor porte des projets numériques à destination des professionnels de santé et des patients. Ces projets nécessitent un accompagnement en conception (UX/UI, design de service) et en pilotage agile.

### Section 6.2. Prestations attendues pour le lot 3

#### 6.2.1. DESIGNUXUI — Design UX/UI

**Activités :**
- Audit d'ergonomie et d'accessibilité (RGAA)
- Conception d'interfaces (wireframes, prototypes haute fidélité)
- Réalisation de tests utilisateurs
- Production de spécifications graphiques (design system)

**Profils :** Designer UX/UI, Ergonome

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| DESIGNUXUI 1 | Refonte d'un écran existant | Faible |
| DESIGNUXUI 2 | Conception d'un nouveau parcours (3-5 écrans) | Moyenne |
| DESIGNUXUI 3 | Conception d'un service complet (>5 parcours) | Grande |

#### 6.2.2. DESIGNSERV — Design de service

**Activités :**
- Cartographie du parcours utilisateur (service blueprint)
- Ateliers co-conception avec les parties prenantes
- Définition du modèle de service cible

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| DESIGNSERV 1 | Cartographie d'un service existant | Faible |
| DESIGNSERV 2 | Co-conception d'un service cible | Moyenne |
| DESIGNSERV 3 | Transformation complète d'un service | Grande |

#### 6.2.3. RECHUX — Recherche Utilisateur

**Activités :**
- Entretiens utilisateurs
- Observations terrain (shadowing)
- Analyse et synthèse des insights
- Personas et scénarios d'usage

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| RECHUX 1 | 5 entretiens + rapport | Faible |
| RECHUX 2 | 10 entretiens + observation terrain + rapport | Moyenne |
| RECHUX 3 | Étude complète (entretiens + observation + tests + personas) | Grande |

#### 6.2.4. DESIGNGRAPH — Création graphique

**Activités :**
- Création d'identité visuelle pour un produit numérique
- Production d'illustrations et icônes
- Adaptation aux chartes graphiques institutionnelles

#### 6.2.5. AGILENUM — Management agile de produit numérique

**Activités :**
- Définition et priorisation du backlog produit
- Animation des cérémonies agiles (sprint planning, rétro, demo)
- Coordination des équipes pluridisciplinaires
- Reporting aux parties prenantes

**Profils :** Product Owner, Scrum Master

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| AGILENUM 1 | Accompagnement < 1 mois | Faible |
| AGILENUM 2 | Accompagnement 1-3 mois | Moyenne |
| AGILENUM 3 | Accompagnement > 3 mois | Grande |

#### 6.2.6. IMPACT — Analyse et mesure d'impact

**Activités :**
- Définition d'indicateurs d'impact (OKR, KPI)
- Mise en place de dispositifs de mesure
- Production de rapports d'impact

---

## Article 7. Lot 4 – Accompagnement des utilisateurs et gestion des projets de recherche

### Section 7.1. Description des besoins

La plateforme EDS-V accueille des projets de recherche portés par des professionnels de santé. Ces projets nécessitent un accompagnement dédié : gestion de projet, support aux utilisateurs, coordination.

### Section 7.2. Prestations attendues pour le lot 4

#### 7.2.1. GESPJTR — Gestion de projets de recherche

**Activités :**
- Accompagnement des porteurs de projets de recherche
- Suivi des jalons et des livrables
- Coordination avec les instances éthiques (CPP, CNIL)
- Reporting aux commanditaires

**Profils :** Chef de Projet Recherche, Coordinateur Clinique

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| GESPJTR 1 | Projet court < 6 mois, équipe réduite | Faible |
| GESPJTR 2 | Projet 6-18 mois, équipe pluridisciplinaire | Moyenne |
| GESPJTR 3 | Projet > 18 mois, multi-sites, multi-partenaires | Grande |

#### 7.2.2. PMO — Assistance à la coordination de projets

**Activités :**
- Consolidation du portefeuille de projets
- Suivi budgétaire et des ressources
- Production de tableaux de bord de pilotage
- Animation des comités de pilotage

**Métriques :**

| UO | Description | Complexité |
|---|---|---|
| PMO 1 | Suivi d'un projet unique | Faible |
| PMO 2 | Coordination de 3 à 7 projets | Moyenne |
| PMO 3 | Pilotage de portefeuille > 7 projets | Grande |

#### 7.2.3. SUPPTIL — Support aux utilisateurs

**Activités :**
- Traitement des demandes et incidents niveau 1/2
- Formation des nouveaux utilisateurs
- Rédaction de la documentation utilisateur (guides, tutoriels)
- Contribution à la base de connaissances

**Profils :** Chargé de support, Formateur

**SLA attendus :**

| Priorité | Délai d'accusé | Délai de résolution |
|---|---|---|
| Critique | 30 min | 4h |
| Haute | 2h | 8h |
| Normale | 4h | 2 jours ouvrés |
| Faible | 1 jour ouvré | 5 jours ouvrés |

---

## Article 8. Conditions d'exécution et suivi contractuel

### Section 8.1. Obligations générales des parties

#### 8.1.1. Obligations du Titulaire

Le Titulaire s'engage à :
- Affecter des ressources qualifiées et en nombre suffisant
- Respecter les délais convenus dans les bons de commande
- Informer le CHU de Valdor de tout événement susceptible d'impacter le bon déroulement des prestations
- Assurer la confidentialité des données de santé traitées (conformément au RGPD et aux référentiels HDS)
- Garantir la sécurité des accès et des traitements

#### 8.1.2. Obligations du CHU de Valdor

Le CHU de Valdor s'engage à :
- Fournir les informations et accès nécessaires à l'exécution des prestations
- Désigner des interlocuteurs référents pour chaque projet
- Valider les livrables dans les délais contractuels
- Mettre à disposition les environnements de développement et de test

### Section 8.2. Organisation et suivi du marché

#### 8.2.1. Chef de projet du Titulaire

Un Chef de Projet unique est désigné par le Titulaire comme interlocuteur principal du CHU de Valdor. Il est garant de la qualité et du respect des délais pour l'ensemble des prestations commandées.

#### 8.2.2. Réunions de suivi

- **Comité opérationnel** : mensuel — suivi de l'avancement des commandes en cours
- **Comité de pilotage** : trimestriel — bilan qualité, indicateurs, difficultés
- **Revue annuelle** : bilan global et perspectives

### Section 8.3. Conditions générales d'exécution

#### 8.3.1. Langue d'exécution

Toutes les prestations (documentation, réunions, livrables) sont réalisées en **langue française**.

#### 8.3.2. Lieu d'exécution

Les prestations sont réalisées :
- Sur site au CHU de Valdor (12, avenue des Sciences — 69500 VALDOR)
- En télétravail, avec accord préalable du chef de projet CHU-V

Les accès aux données de santé ne peuvent être effectués que depuis des postes sécurisés, conformément à la politique de sécurité du SI du CHU de Valdor.

#### 8.3.3. Intervenants

Le Titulaire communique la liste des intervenants prévus pour chaque bon de commande. Tout changement d'intervenant doit faire l'objet d'un accord préalable du CHU de Valdor.

**Profils minimum requis par lot :**

| Profil | Expérience minimale | Lot concerné |
|---|---|---|
| Ingénieur Big Data / Data Engineer | 3 ans | Lot 1, Lot 2 |
| Data Scientist / ML Engineer | 3 ans | Lot 2 |
| Designer UX/UI | 3 ans | Lot 3 |
| Chef de projet (certification PMP ou équivalent) | 5 ans | Tous lots |
| Ingénieur sécurité (certification CISSP ou équivalent) | 4 ans | Lot 1 |

### Section 8.4. Modalités spécifiques d'exécution

#### 8.4.1. Outils

Le Titulaire utilise les outils désignés par le CHU de Valdor :
- Gestion de projet et tickets : **Jira / Confluence**
- Versionnement : **GitLab** (instance interne CHU-V)
- Communication : **Mattermost** (messagerie interne)
- Partage documentaire : **SharePoint** (instance CHU-V)

#### 8.4.2. Initialisation du marché

En début de marché, le Titulaire réalise une prestation d'initialisation comprenant :
1. Prise de connaissance de l'environnement technique et organisationnel
2. Présentation des équipes et de l'organisation proposée
3. Mise en place des outils et accès nécessaires
4. Production d'un plan de charge prévisionnel

**Délai :** La prestation d'initialisation doit être réalisée dans les **6 semaines** suivant la notification du marché.

**Livrable :** Dossier d'initialisation présenté lors d'une réunion de lancement.

#### 8.4.3. Réversibilité en fin de marché

La prestation de réversibilité comprend :
1. Constitution d'un dossier de reversibilité (documentation, code source, paramétrage)
2. Formation des équipes du CHU-V ou du nouveau prestataire
3. Période d'assistance à la reprise (minimum 3 mois)

**Délai de déclenchement :** 6 mois avant la fin du marché ou à tout moment sur demande du CHU-V.

### Section 8.5. Bons de commande

Le CHU de Valdor commande les prestations par émission de **Bons de Commande (BC)** référençant les unités d'œuvre du présent CCTP.

Chaque BC précise :
- Les unités d'œuvre commandées (type, complexité, quantité)
- Les délais de réalisation
- Les conditions de livraison et de validation

Le Titulaire dispose de **5 jours ouvrés** pour émettre un devis suite à la réception d'une demande de prestation.

### Section 8.6. Suivi et validation des prestations

#### 8.6.1. Validation des livrables

Chaque livrable fait l'objet d'une validation par le chef de projet CHU-V :
- **Accusé de réception** dans les 2 jours ouvrés suivant la remise du livrable
- **Retour de commentaires** dans les 10 jours ouvrés
- **Validation définitive** après correction des éventuels points de non-conformité

#### 8.6.2. Indicateurs de qualité de service

| Indicateur | Cible | Mesure |
|---|---|---|
| Respect des délais contractuels | ≥ 95% | Mensuelle |
| Taux de livrables acceptés sans réserve | ≥ 85% | Mensuelle |
| Taux de disponibilité des infrastructures MCO | ≥ 99,5% | Mensuelle |
| Délai moyen de traitement des incidents Lot 4 | ≤ SLA définis | Mensuelle |
| Satisfaction globale des commanditaires | ≥ 3,5 / 5 | Trimestrielle |

### Section 8.7. Traitement des incidents et litiges

#### 8.7.1. Traitement des incidents

En cas d'incident, le Titulaire :
1. Accuse réception dans le délai convenu
2. Réalise un diagnostic et propose un plan de correction
3. Informe le CHU-V de l'avancement de la résolution
4. Produit un rapport post-incident pour les incidents critiques

#### 8.7.2. Traitement des litiges

Tout litige est escaladé selon le schéma suivant :
1. Niveau opérationnel : résolution entre chefs de projet (5 jours)
2. Niveau direction : escalade aux directions concernées (15 jours)
3. Médiation : recours à un médiateur désigné conjointement
4. Voie juridique : si aucune résolution amiable n'est trouvée

---

## Article 9. Annexes

### Annexe 1 — Grille des indicateurs de qualité de service (QoS)

*(Document séparé joint à la consultation)*

### Annexe 2 — Politique Générale de Sécurité du SI (PGSSI-CHU-V)

Tout intervenant du Titulaire doit respecter la PGSSI du CHU de Valdor. Une formation de sensibilisation est obligatoire avant tout accès aux systèmes.

*(Document séparé joint à la consultation)*

### Annexe 3 — Sécurité Fournisseur

Exigences de sécurité applicables aux prestataires accédant au SI du CHU de Valdor, incluant les obligations RGPD, HDS et les exigences de traçabilité.

*(Document séparé joint à la consultation)*

### Annexe 4 — Cadre de Cohérence Technique (CCT-CHU-V)

Référentiel des technologies et standards validés par la DSI du CHU de Valdor.

*(Document séparé joint à la consultation)*

---

*Fin du document — Consultation N° 25-12 IT — CHU de Valdor*