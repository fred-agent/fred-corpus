# Script démo Fred — Cellule de veille EM · 22/07/2026

Fil rouge à annoncer en ouverture : « Trois anomalies ont été détectées aujourd'hui sur notre
réseau de goniométrie côtière. On va mener l'enquête avec Fred : d'abord vérifier qu'on peut
faire confiance à l'agent, puis interroger les données, croiser avec nos procédures, et finir
sur la situation tactique en temps réel. »

---

## Acte 1 — La confiance d'abord (rien à taper)

Montrer les résultats d'éval : 13/14 sur l'agent SQL, run hybride.
Ouvrir la trace du cas raté (ewtracks-13) et dérouler en 30 s :
« L'agent a répondu juste à une autre question — l'écart au seuil réglementaire de la SOP
au lieu du profil propre du navire. Réponse chiffrée, propre, un relecteur humain l'aurait
validée. Seule l'éval avec vérité terrain l'a vue. C'est exactement pour ça qu'on évalue. »

---

## Acte 2 — L'agent SQL en direct

**Q1 — échauffement**
```
Combien de navires suivons-nous aujourd'hui, et quelle est la répartition civils/militaires ?
```
Attendu : 40 navires — 31 civils, 9 militaires. Source citée : dataset tabulaire.

**Q2 — agrégation**
```
Quelle station radar a enregistré le plus de détections, et combien ?
```
Attendu : RAD-TLN (Cap Cepet, Toulon), 1 775 détections.

**Q3 — la question vedette (le trou n'existe dans aucune colonne)**
```
Y a-t-il des navires qui ont cessé d'émettre plus longtemps que la cadence normale de 5 minutes ?
```
Attendu : MV Costa Brava (CIV-ES-401), interruption de 40 min.
À l'oral : « Cette réponse n'est écrite nulle part — l'agent a comparé les timestamps
consécutifs de chaque piste. »

**Q3bis — relance conversationnelle**
```
Entre quelles heures exactement, et que faisait-il avant de disparaître ?
```
Attendu : 13:00Z → 13:40Z ; route ~85° avant, réacquisition avec route ~140°.

**Q4 — le pivot vers les procédures**
```
Liste-moi les anomalies marquées de la journée.
```
Attendu : 12:30Z Costa Brava (freq_out_of_profile), 12:30Z Atlantique (freq_out_of_profile),
12:40Z Surcouf (df_azimuth_mismatch), 13:40Z Costa Brava (track_gap).
Transition : « Trois événements. Voyons ce qu'en disent nos procédures. »

---

## Acte 3 — L'hybride SQL + RAG

**Q5 — l'exemption exercice (vérification des 3 conditions)**
```
Le Surcouf présente un écart d'azimut à 12:40Z — comment dois-je classer cette anomalie selon la SOP ?
```
Attendu : +90° > seuil de 10° → NIVEAU 3/P-21 en première lecture, MAIS exemption exercice :
bulletin 2026-203, entrée 203-E (TRIDENT ÉCLAIR), créneau 12:30–13:00Z ✓, zone Iroise ✓,
unité participante ✓ → reclassé NIVEAU 0, artefact d'exercice, main courante.
À l'oral : « L'agent vérifie les trois conditions de l'exemption, pas juste "il y avait un exercice". »

**Q6 — la corrélation multi-bassins**
```
Les deux émissions hors profil de 12:30Z peuvent-elles être liées, et comment les traiter ?
```
Attendu : même minute, deux bassins à ~817 km (golfe du Lion / baie de Seine), 25,5 et
20,8 MHz > plafond civil 16 MHz → règle de corrélation multi-bassins → NIVEAU 3, P-21,
rapport CIRCE sous 2 h. Le bulletin ne déclare RIEN dans ces bassins.

**Q7 — le grand final acte 3 (= ewhybrid-6, déjà évaluée)**
```
Prépare la synthèse officier de permanence des anomalies du jour : niveau de classement, procédure applicable, référence du bulletin consultée, et événements restant inexpliqués.
```
Attendu : Surcouf → NIVEAU 0 (203-E) ; émissions coordonnées → NIVEAU 3/P-21 ;
track_gap Costa Brava → NIVEAU 2/P-12. Restent inexpliqués : les émissions coordonnées et
le trou + déviation — et deux des trois impliquent le même navire.
Transition : « Le même navire, deux fois. Et où est-il, là, maintenant ? »

---

## Acte 4 — MCP temps réel + carte

**Q8 — le live**
```
Où se trouve le Costa Brava en ce moment, et que fait-il ?
```
Attendu (horloge MCP ~14:00–15:00Z) : cap ~140°, ~12,5 nœuds, route vers les approches
de Toulon.

**Q9 — le rideau**
```
Affiche-moi la situation tactique : sa position actuelle, sa trace depuis 12:00Z, et les couvertures radar de la zone.
```
Attendu : carte Leaflet — trace déviée du Costa Brava, cercles de couverture, Toulon en ligne de mire.

---

## Filets de sécurité

- Réponse à côté en live → « regardons comment l'agent a raisonné » : ouvrir la trace,
  c'est une démo de transparence, pas un échec.
- Question de la salle sur le tir à l'île du Levant → planifié demain 23/07 (203-C), hors journée.
- Question sur la maintenance RAD-ATL → 05:00–05:45, avant le début des données (06:00Z), aucun impact.
- Heures : tout est en UTC (Z). Le dire une fois en ouverture.
- Questions longues : copier-coller depuis ce fichier, ne jamais retaper en live.
