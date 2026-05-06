# FICHE RÉFÉRENCE PROJET — THALES SERVICES NUMÉRIQUES

**Référence interne :** TSN-DSP-REF-2022-018
**Business Line :** Systèmes d'Information de Sécurité Critiques
**Business Unit :** Défense et Secteur Public
**Statut :** Projet clôturé — réception définitive en décembre 2023

---

## 1. Identification du projet

| Champ | Valeur |
|---|---|
| **Titre** | Refonte du téléservice de demande d'autorisation d'urbanisme pour une métropole française |
| **Code projet** | URBA-METROBEL-2022 |
| **Client** | Métropole de Belcourt (collectivité territoriale, 480 000 habitants) |
| **Commanditaire** | Direction de l'Aménagement et du Droit des Sols |
| **Période de réalisation** | Janvier 2022 — Décembre 2023 (24 mois) |
| **Montant global** | 1,35 M€ HT |
| **Modèle contractuel** | Marché public à **prix forfaitaire (FFP)** — obligation de résultat, découpé en 4 tranches (ferme + 3 conditionnelles) |
| **Type de procédure** | MAPA (Marché à Procédure Adaptée), < seuils UE |

---

## 2. Contexte client

La Métropole de Belcourt gère l'instruction d'environ 9 500 dossiers d'urbanisme par an (permis de construire, déclarations préalables, certificats d'urbanisme) pour le compte de ses 34 communes membres. L'outil historique — un client lourd déployé en 2008, connecté à une base Oracle — était devenu obsolète : ergonomie dépassée, absence d'interface citoyen en ligne, non-conformité aux exigences du **décret "Saisine par Voie Électronique" (SVE)** et aux échéances de la loi **ELAN** imposant la dématérialisation complète de l'instruction au 1er janvier 2022.

Les enjeux exprimés au démarrage :
- Permettre aux citoyens et aux professionnels (architectes, notaires) de déposer leurs demandes 100 % en ligne
- Offrir un back-office d'instruction ergonomique aux 42 agents instructeurs
- Assurer l'interopérabilité avec **Plat'AU** (plateforme nationale des autorisations d'urbanisme)
- Garantir l'accessibilité **RGAA 4.1 niveau AA**
- Respecter les exigences du **RGS** (Référentiel Général de Sécurité) niveau 2 étoiles

---

## 3. Périmètre et prestations réalisées

Thales Services Numériques est intervenu comme titulaire unique, équipe de 8 à 12 ETP selon les phases.

### Phase 1 — Cadrage et conception (2022)
- Ateliers de co-conception avec les agents instructeurs et un panel de citoyens
- Production d'un design system accessible (RGAA 4.1)
- Spécifications fonctionnelles générales (SFG) et détaillées (SFD)
- Architecture technique et dossier de sécurité

### Phase 2 — Développement (2022-2023)
- Développement du portail citoyen (formulaires dynamiques Cerfa, suivi des demandes, notifications)
- Développement du back-office instructeur (workflow d'instruction, édition des arrêtés, courriers types)
- Intégration avec **Plat'AU** via l'API de la DGALN
- Intégration avec **FranceConnect** pour l'authentification citoyenne
- Interfaçage avec le SIG de la métropole (cartographie cadastrale)
- Édition automatisée des documents réglementaires (PDF signés électroniquement)

### Phase 3 — Déploiement et accompagnement (2023)
- Reprise de données depuis l'ancien outil (12 ans d'historique, 98 000 dossiers)
- Formation des 42 agents instructeurs (sessions présentielles + e-learning)
- Déploiement progressif sur les 34 communes (vague pilote, puis généralisation)
- Hypercare pendant les 3 mois suivant la mise en production

---

## 4. Stack technique

- **Front-end :** React 18, TypeScript, composants issus du Design System de l'État (DSFR), tests E2E Playwright
- **Back-end :** Node.js (NestJS), API REST, PostgreSQL 15
- **Workflow :** moteur BPMN open source (Camunda)
- **Édition documentaire :** templates DOCX/PDF (docxtemplater + LibreOffice headless)
- **Signature électronique :** intégration avec le parapheur de la collectivité (i-Parapheur)
- **Authentification :** FranceConnect + Keycloak (pour les agents)
- **Hébergement :** datacenter souverain français (prestataire SecNumCloud), infra Kubernetes
- **CI/CD :** GitLab CI, SonarQube, revues de code systématiques

**Conformités :** RGAA 4.1 niveau AA (audit externe passé), RGS ** (2 étoiles), RGPD (registre de traitement produit et validé par le DPO de la métropole).

---

## 5. Organisation et pilotage

- **Équipe Thales :** 1 Directeur de projet, 1 Architecte logiciel, 1 Product Owner, 1 Designer UX/UI, 5 à 8 développeurs (front + back), 1 référent accessibilité
- **Gouvernance :** comité de suivi hebdomadaire, COPIL mensuel, comité stratégique trimestriel avec la DGA de la métropole
- **Méthode :** Scrum (sprints 2 semaines), démos aux utilisateurs finaux toutes les 4 semaines
- **Engagement contractuel :** obligation de résultat sur les fonctionnalités de chaque tranche, pénalités de retard plafonnées à 5 % du montant de la tranche

---

## 6. Résultats et bénéfices mesurés

| Indicateur | Avant projet | Après projet | Delta |
|---|---|---|---|
| Part des demandes dématérialisées | 0 % | 87 % (citoyens), 96 % (pros) | — |
| Délai moyen d'instruction | 68 jours | 41 jours | -40 % |
| Satisfaction des usagers (enquête post-dépôt) | n/a | 4,2 / 5 | — |
| Taux d'accessibilité RGAA (audit externe) | n/a | 97 % conforme niveau AA | — |
| Appels au standard pour questions "où en est mon dossier" | ~650/mois | ~90/mois | -86 % |
| Respect des jalons contractuels | — | 4/4 tranches livrées en délai | — |

**Reconnaissance externe :** projet cité comme exemple dans le guide "Dématérialisation des autorisations d'urbanisme" publié par la DGALN en 2024.

---

## 7. Points forts différenciants

- **Maîtrise du cadre réglementaire urbanisme** : la connaissance fine de Plat'AU, des Cerfa et des workflows d'instruction a permis d'éviter les écueils classiques (formulaires incomplets, rejets Plat'AU).
- **Accessibilité de premier plan** : l'intégration précoce d'un référent accessibilité dans l'équipe projet a permis d'atteindre 97 % de conformité RGAA dès la première mise en production, sans phase de remédiation.
- **Engagement FFP tenu** : les 4 tranches ont été livrées dans les délais contractuels, sans application de pénalités — un résultat atypique sur ce type de projet territorial.
- **Design system de l'État (DSFR)** : utilisation rigoureuse du DSFR, ce qui a réduit le coût d'UI et facilité l'acceptation par les équipes communication de la métropole.

---

## 8. Difficultés rencontrées et enseignements

- **Reprise de données** plus complexe que prévu : l'ancien modèle Oracle contenait de nombreuses incohérences (dates invalides, champs texte libre au lieu de références structurées). Un chantier de nettoyage a été ajouté en avenant.
- **Changement de version de Plat'AU** en cours de projet : la DGALN a publié une nouvelle version d'API mi-2022, imposant une réécriture partielle du connecteur. Enseignement : prévoir une clause de révision pour les dépendances externes évolutives.
- **Conduite du changement** sous-estimée initialement pour les petites communes (manque de culture numérique chez certains secrétaires de mairie) — un programme de formation étendu a été mis en place.

---

## 9. Contact interne Thales

- **Directeur de projet :** [ANONYMISÉ] — disponible pour partage d'expérience
- **Architecte logiciel référent :** [ANONYMISÉ]
- **Centre de compétence concerné :** CoC Services Numériques aux Collectivités — Thales Services Numériques

---

*Fiche rédigée dans le cadre du partage de références pour les opportunités commerciales de la BL SISC. Diffusion restreinte équipe Bid Management.*
