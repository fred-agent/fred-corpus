# FICHE RÉFÉRENCE PROJET — THALES SERVICES NUMÉRIQUES

**Référence interne :** TSN-DSP-REF-2022-031
**Business Line :** Systèmes d'Information de Sécurité Critiques
**Business Unit :** Défense et Secteur Public
**Statut :** Projet en cours — phase de run (maintenance évolutive depuis 2023)

---

## 1. Identification du projet

| Champ | Valeur |
|---|---|
| **Titre** | Plateforme souveraine de supervision cyber pour un OIV du secteur de l'énergie |
| **Code projet** | SOC-ENERGIA-2020 |
| **Client** | EnerGrid France (OIV — Opérateur d'Importance Vitale, secteur énergie) |
| **Commanditaire** | Direction Cybersécurité — CISO Office |
| **Période de réalisation** | Septembre 2020 — présent (run jusqu'en 2026) |
| **Montant global** | 7,2 M€ HT cumulés sur 5 ans (marché cadre + avenants) |
| **Modèle contractuel** | Marché public de prestations intellectuelles — **régie (T&M)** sur unités d'œuvre homme.jour, avec engagement de moyens |
| **Type de procédure** | Appel d'offres restreint formalisé, procédure avec négociation |
| **Classification** | Diffusion Restreinte — habilitation Confidentiel Défense requise pour 4 profils |

---

## 2. Contexte client

EnerGrid France est un Opérateur d'Importance Vitale désigné au titre du Code de la défense, assurant la distribution d'électricité sur plusieurs régions françaises. À ce titre, l'entreprise est soumise aux obligations de la **LPM (Loi de Programmation Militaire)** et de la directive **NIS 2**, ce qui impose :
- Un SOC (Security Operation Center) opéré depuis le territoire national
- Des technologies qualifiées ou en cours de qualification par l'ANSSI
- Une souveraineté stricte des données de journalisation (aucun flux sortant hors UE)
- Une traçabilité des accès à vocation d'audit réglementaire (CNIL, ANSSI, ACN)

Le projet portait sur la refonte complète du SOC historique, construit sur un SIEM propriétaire américain jugé non conforme aux exigences de souveraineté post-LPM.

---

## 3. Périmètre et prestations réalisées

Thales Services Numériques est intervenu comme titulaire principal en co-traitance avec une ESN française spécialisée en cyberdéfense. Équipe dimensionnée de **24 à 32 ETP** selon les phases, tous habilités.

### Phase 1 — Cadrage et architecture (2020-2021)
- Audit du SOC existant et des flux de collecte (1 800 sources)
- Définition de l'architecture cible sur stack open source souveraine
- Rédaction du Dossier d'Architecture Technique (DAT) et du Dossier d'Exploitation (DEX)
- Homologation RGS (Référentiel Général de Sécurité) de l'architecture cible

### Phase 2 — Construction et migration (2021-2022)
- Déploiement d'une plateforme de collecte et corrélation basée sur **OpenSearch**, **Vector** et **Cribl**
- Développement de 220 règles de détection custom (format Sigma) couvrant les TTPs MITRE ATT&CK applicables au secteur énergie
- Intégration avec les systèmes SCADA/ICS via des connecteurs dédiés (protocoles IEC 61850, Modbus)
- Migration progressive des 1 800 sources, avec double run de 4 mois
- Mise en place d'une interface analyste sur mesure (React + FastAPI)

### Phase 3 — Run et amélioration continue (2023-présent)
- Build continu de nouveaux cas d'usage (en moyenne 15 nouvelles règles de détection par trimestre)
- Veille sur les menaces sectorielles et intégration du threat intelligence (MISP)
- Accompagnement des analystes N1/N2 du client (coaching, formation, rédaction de runbooks)
- Tests d'intrusion semestriels et red-teaming annuel
- Maintenance des composants open source et gestion des CVE

---

## 4. Stack technique

- **Collecte :** Vector, Cribl Stream, agents Wazuh
- **Stockage / recherche :** OpenSearch cluster 18 nœuds (1,2 Po de logs chauds, rétention 13 mois), MinIO pour archivage froid
- **Corrélation et détection :** Sigma, Chainsaw, moteur custom développé en Rust
- **Threat intelligence :** MISP, OpenCTI
- **Orchestration SOAR :** StackStorm (développements custom)
- **Visualisation analyste :** OpenSearch Dashboards + interface web custom (React + FastAPI)
- **Infrastructure :** VMware on-premise, durcissement CIS Level 2, chiffrement au repos (LUKS) et en transit (mTLS)
- **Outils dev :** GitLab CE on-premise (aucun outil cloud), SonarQube, ansible-vault

**Note souveraineté :** aucun composant SaaS, aucune dépendance cloud US/Chine. Toute la chaîne logicielle est auditée et les binaires sont reconstruits depuis les sources dans la supply chain interne Thales.

---

## 5. Organisation et pilotage

- **Équipe Thales (cœur) :** 1 Directeur de programme, 1 Architecte cybersécurité sénior (habilité CD), 2 Ingénieurs sécurité sénior, 12 à 18 analystes/ingénieurs SOC selon les phases, 1 PMO, 1 RSSI projet
- **Co-traitance :** 6 à 10 ETP d'un partenaire français spécialisé en ICS/OT
- **Gouvernance :** comité technique hebdomadaire, comité de pilotage mensuel (présence CISO), revue stratégique trimestrielle avec le COMEX d'EnerGrid
- **Méthode :** cycle en V adapté pour les phases 1 et 2 (contraintes d'homologation), agilité encadrée pour la phase 3 (sprints 2 semaines, backlog de détection)
- **Sécurité opérationnelle :** tous les intervenants disposent d'un compte dédié sur l'infrastructure client, accès via bastion, revues de droits trimestrielles

---

## 6. Résultats et bénéfices mesurés

| Indicateur | Avant projet | Après projet | Delta |
|---|---|---|---|
| Nombre de sources collectées | 1 800 (partielles) | 4 400 (exhaustives) | +144 % |
| MTTD (Mean Time To Detect) | 4 h 30 | 18 min | -93 % |
| MTTR (Mean Time To Respond) | 12 h | 1 h 45 | -85 % |
| Règles de détection en production | 45 | 620 | ×13,8 |
| Couverture MITRE ATT&CK (Enterprise) | 22 % | 71 % | +49 pts |
| Conformité exigences LPM / NIS 2 | partielle | totale | — |
| Dépendance à des éditeurs non-UE | forte (SIEM US) | nulle | — |

**Reconnaissance externe :** plateforme auditée par l'ANSSI en 2023, rapport d'audit sans non-conformité majeure. Architecture présentée aux Assises de la Sécurité 2023 comme référence de SOC souverain.

---

## 7. Points forts différenciants

- **Souveraineté bout en bout** : tous les choix technologiques ont été justifiés devant l'ANSSI, et la chaîne de build est reproductible depuis les sources — un niveau d'exigence que peu de concurrents sont capables de tenir.
- **Expertise OT/ICS** : la capacité à intégrer des sources SCADA et à développer des cas d'usage de détection adaptés aux environnements industriels a été un facteur décisif au moment du choix (différenciateur explicite dans le PV d'attribution).
- **Habilitations et continuité humaine** : équipe cœur habilitée CD, maintenue stable sur 5 ans, ce qui a permis une montée en compétence progressive et une relation de confiance avec le CISO.
- **Transfert de compétences massif** : 35 analystes du client formés sur la nouvelle plateforme, avec une documentation interne (runbooks, playbooks, parcours d'onboarding) rédigée en français et maintenue à jour.

---

## 8. Difficultés rencontrées et enseignements

- **Homologation RGS plus longue que prévue** (+3 mois) : les itérations avec l'ANSSI sur le dossier d'architecture ont été nombreuses. Enseignement : budgéter systématiquement 4 à 6 mois pour les homologations RGS sur projets OIV.
- **Recrutement d'habilités** : difficulté à trouver des profils disposant déjà de l'habilitation Confidentiel Défense. Une partie de l'équipe a dû suivre la procédure d'habilitation en parallèle (délai 6-9 mois). À anticiper très en amont sur ce type de projet.
- **Co-traitance complexe** : la coordination avec le partenaire OT/ICS a nécessité une formalisation stricte des responsabilités (matrice RACI contractuelle). Enseignement : ne pas sous-estimer le temps de pilotage de la co-traitance en phase de cadrage.

---

## 9. Contact interne Thales

- **Directeur de programme :** [ANONYMISÉ] — disponible pour partage d'expérience
- **Architecte cybersécurité référent :** [ANONYMISÉ] (habilité Confidentiel Défense)
- **Centre de compétence concerné :** CoC SOC & Cyber Défense — Thales Services Numériques

---

*Fiche rédigée dans le cadre du partage de références pour les opportunités commerciales de la BL SISC. Diffusion Restreinte — ne pas diffuser hors équipe Bid Management habilitée.*
