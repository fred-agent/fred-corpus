# FICHE RÉFÉRENCE PROJET — THALES SERVICES NUMÉRIQUES

**Référence interne :** TSN-DSP-REF-2022-009
**Business Line :** Systèmes d'Information de Sécurité Critiques
**Business Unit :** Défense et Secteur Public
**Statut :** Projet clôturé — réception définitive en juin 2024

---

## 1. Identification du projet

| Champ | Valeur |
|---|---|
| **Titre** | Plateforme de données et IA pour l'imagerie médicale — Institut de Cancérologie Léon-Valmont |
| **Code projet** | IMG-ICLV-2022 |
| **Client** | Institut de Cancérologie Léon-Valmont (ICLV) — CLCC (Centre de Lutte Contre le Cancer) |
| **Commanditaire** | Direction de la Recherche Clinique et Translationnelle |
| **Période de réalisation** | Avril 2022 — Juin 2024 (27 mois) |
| **Montant global** | 3,1 M€ HT |
| **Modèle contractuel** | Marché public — **accord-cadre mono-attributaire à bons de commande**, BPU unités d'œuvre + tranches forfaitaires pour les lots produits |
| **Type de procédure** | Appel d'offres ouvert formalisé (> seuils UE) |

---

## 2. Contexte client

L'ICLV est un Centre de Lutte Contre le Cancer (CLCC) de référence régionale, prenant en charge environ 42 000 patients par an (dont 9 500 nouveaux cas) et opérant un service d'imagerie médicale parmi les plus actifs de son territoire (scanners, IRM, TEP-TDM, mammographies). L'institut pilote par ailleurs une quinzaine d'essais cliniques actifs en oncologie et participe à plusieurs cohortes nationales.

Les enjeux exprimés au démarrage :
- Constituer un **entrepôt d'imagerie** exploitable à des fins de recherche (radiomics, IA)
- Mettre en place une **plateforme MLOps** permettant aux équipes de recherche de développer, entraîner et déployer des modèles d'IA sur imagerie de manière encadrée
- Assurer l'**interopérabilité FHIR** avec les SI cliniques et le DPI pour enrichir les images avec les métadonnées patient et traitement
- Garantir la **conformité HDS et RGPD renforcée** (données sensibles de santé, pseudonymisation systématique, registre de traitements, AIPD)
- Respecter la **doctrine du Health Data Hub** et préparer l'interconnexion future avec le HDH pour les projets nationaux

---

## 3. Périmètre et prestations réalisées

Thales Services Numériques est intervenu comme titulaire unique, équipe de 10 à 14 ETP selon les phases.

### Lot 1 — Infrastructure et stockage
- Déploiement d'un cluster Kubernetes on-premise (9 nœuds) sur une infrastructure certifiée HDS
- Mise en place d'un stockage objet MinIO (S3-compatible) pour l'imagerie DICOM (180 To initiaux, croissance +60 To/an)
- Intégration d'un nœud de calcul GPU dédié (6 Nvidia A100) pour l'entraînement et l'inférence
- Durcissement sécurité : HashiCorp Vault, Keycloak (OIDC), supervision Prometheus/Grafana/Loki

### Lot 2 — Entrepôt d'imagerie et interopérabilité
- Connecteur **DICOMweb** vers le PACS de l'institut avec pseudonymisation à la volée (CTP — Clinical Trial Processor)
- Ingestion et normalisation des métadonnées cliniques au format **FHIR R4** (patients, études, diagnostics, traitements)
- Mapping partiel OMOP CDM pour les cohortes partagées avec d'autres CLCC
- Pipelines Spark/Python pour l'extraction de caractéristiques radiomiques (pyradiomics)
- Outillage qualité de données (Great Expectations) et lignage (OpenLineage)

### Lot 3 — Plateforme MLOps et IA
- **JupyterHub** multi-utilisateurs avec environnements préconfigurés (PyTorch, MONAI, nnU-Net)
- Pipeline MLOps complet : **MLflow** (tracking, registry), **Argo Workflows** (training pipelines), **Triton Inference Server** (déploiement)
- Développement en co-construction de **2 modèles IA** mis en production :
  - Segmentation automatique de tumeurs sur IRM pelviennes (MONAI + nnU-Net)
  - Classification radiologique d'aide au staging ganglionnaire sur TEP-TDM
- Monitoring de dérive des modèles en production (Evidently)

### Lot 4 — Accompagnement et réversibilité
- Formation de 28 chercheurs et radiologues à JupyterHub et aux bonnes pratiques MLOps
- Rédaction du DAT, du DEX et du dossier de conformité HDS
- Accompagnement de 7 projets de recherche clinique sur la plateforme
- Dossier de réversibilité et transfert de compétences vers la DSI de l'institut (3 mois)

---

## 4. Stack technique

- **Orchestration :** Kubernetes (Rancher), Argo Workflows, Argo CD
- **Stockage :** MinIO (S3), PostgreSQL, Elasticsearch, Orthanc (PACS de recherche)
- **Traitement :** Apache Spark, Python, pyradiomics, pandas
- **Imagerie / IA :** PyTorch, MONAI, nnU-Net, Triton Inference Server, MLflow, JupyterHub
- **Interopérabilité :** HAPI FHIR, DICOMweb, CTP (Clinical Trial Processor)
- **Observabilité :** Prometheus, Grafana, Loki, OpenTelemetry
- **Sécurité :** HashiCorp Vault, Keycloak (OIDC), SonarQube, Trivy
- **CI/CD :** GitLab CI, ArgoCD

**Conformités :** hébergement HDS, RGPD (AIPD validée par le DPO), pseudonymisation CTP conforme aux préconisations du HDH.

---

## 5. Organisation et pilotage

- **Équipe Thales :** 1 Directeur de projet, 1 Architecte Data/IA, 1 Responsable sécurité, 2 Data Engineers, 3 Data Scientists (dont 1 spécialisé imagerie médicale), 2 DevOps, 1 PMO
- **Gouvernance :** comité opérationnel bi-mensuel, COPIL trimestriel avec la Direction de la Recherche, revue scientifique semestrielle avec un comité de radiologues et oncologues
- **Méthode :** Scrum adapté (sprints 2 semaines), backlog partagé Jira, démos régulières aux équipes de recherche
- **Co-construction recherche :** implication directe de 4 radiologues de l'institut dans les revues de sprints IA

---

## 6. Résultats et bénéfices mesurés

| Indicateur | Avant projet | Après projet | Delta |
|---|---|---|---|
| Temps de constitution d'une cohorte imagerie annotée | 4 à 6 mois | 3 semaines | -85 % |
| Nombre de projets de recherche IA supportés | 2 | 11 | ×5,5 |
| Disponibilité plateforme MCO | 96,8 % | 99,6 % | +2,8 pts |
| Délai de mise en production d'un modèle (du notebook au serving) | n/a | 9 jours médian | — |
| Volumétrie d'imagerie indexée et requêtable | 0 | 180 To (≈ 2,1 M examens) | — |
| Publications scientifiques s'appuyant sur la plateforme | 0 | 6 (dont 2 en Q1) | — |

**Reconnaissance externe :** projet présenté au congrès **Journées Francophones de Radiologie (JFR) 2024** dans la session "IA et entrepôts d'imagerie" et mentionné dans le rapport d'activité 2024 d'Unicancer comme exemple de plateforme recherche clinique de référence.

---

## 7. Points forts différenciants

- **Expertise conjointe imagerie médicale + MLOps** : capacité à opérer sur toute la chaîne, du PACS à l'inférence industrialisée, sans recourir à plusieurs sous-traitants. Peu de concurrents disposent simultanément de compétences DICOM/CTP, FHIR, et MLOps industriel.
- **Approche "plateforme produit"** : adoption rapide par les chercheurs grâce à une feuille de route trimestrielle visible et à un canal de support dédié — même logique qu'un projet interne de type "Platform as a Product".
- **Conformité HDS nativement intégrée** : architecture validée HDS dès le cadrage, sans phase de remédiation tardive. DPO de l'institut intégré dans les comités techniques dès le sprint 0.
- **Continuité humaine** : le Directeur de projet, l'Architecte Data/IA et le Data Scientist imagerie ont été maintenus sur l'ensemble des 27 mois — facteur explicitement cité par la Direction de la Recherche dans la revue finale comme ayant été décisif sur la confiance accordée.

---

## 8. Difficultés rencontrées et enseignements

- **Pseudonymisation DICOM plus complexe que prévue** : certains champs DICOM propriétaires de constructeurs (Siemens, GE) contenaient des identifiants patients non standards. La chaîne CTP a dû être enrichie par des règles custom (+6 semaines de travail). Enseignement : auditer finement les en-têtes DICOM réels avant de chiffrer la prestation de pseudonymisation.
- **Montée en charge GPU** : les équipes de recherche ont rapidement saturé les 6 A100 dès le 8ᵉ mois. Un mécanisme de quotas et d'ordonnancement a dû être ajouté en avenant. Enseignement : prévoir dès le cadrage un module de gestion des ressources partagées sur les plateformes multi-équipes.
- **Conduite du changement MLOps** : certains chercheurs habitués à des workflows locaux sur station GPU ont eu du mal à adopter la discipline MLflow (logging des runs, versioning). Un programme de "pair MLOps" (binômage avec un Data Scientist Thales pendant 2 sprints) a fortement accéléré l'adoption.

---

## 9. Contact interne Thales

- **Directeur de projet :** [ANONYMISÉ] — disponible pour partage d'expérience
- **Architecte Data/IA référent :** [ANONYMISÉ]
- **Centre de compétence concerné :** CoC Data Platforms Santé — Thales Services Numériques

---

*Fiche rédigée dans le cadre du partage de références pour les opportunités commerciales de la BL SISC. Diffusion restreinte équipe Bid Management.*
