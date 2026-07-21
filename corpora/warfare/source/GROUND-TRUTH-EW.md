# Vérité terrain — ship_tracks_enriched.csv (démo veille EM)

Données synthétiques. Fenêtre 2025-08-31 06:00Z → 18:00Z, cadence 5 min (145 pas).
Les 72 lignes du fichier original de l'équipe GE sont préservées (12:00–12:50Z),
à une exception près : 4 navires ont été translatés en mer (positions originales à terre),
cinématique, fréquences, signaux et erreurs d'azimut préservés — dont le +90° du Surcouf.
Translatés : MV Provence, MV Atlas, FS Surcouf, MV Atlantique.

## Chiffres clés
- Lignes : 5793 | Navires : 40 (9 militaires, 31 civils)
- Détections par radar : {'RAD-ENG': 1450, 'RAD-MRS': 438, 'RAD-TLN': 1775, 'RAD-ATL': 725, 'RAD-COR': 390, 'RAD-BRE': 1015}
- Référentiels : 9 ports (ajout Ajaccio), 6 radars (ajout RAD-COR Cap Corse)

## Anomalies (fil rouge de la démo)
1. 12:30Z — MV Costa Brava (CIV-ES-401) : freq_out_of_profile, golfe du Lion, RAD-MRS
2. 12:30Z — MV Atlantique (CIV-FR-102) : freq_out_of_profile, baie de Seine, RAD-ENG (même minute, autre bassin)
3. 12:40Z — FS Surcouf (MIL-FR-002) : df_azimuth_mismatch, mer d'Iroise, écart azimut +90.0° exactement
4. 13:00→13:40Z — MV Costa Brava : trou de tracking (aucune ligne 13:05–13:35, 7 pas manquants),
   réacquisition 13:40Z marquée track_gap, puis route déviée au SE (~140°) vers les approches de Toulon

## Pièges volontaires pour l'agent SQL
- 'Combien d'anomalies ?' : 4 lignes marquées, mais 3 événements scriptés + 1 réacquisition — et le trou
  lui-même (lignes absentes) n'est détectable que par analyse des timestamps consécutifs.
- Le Costa Brava et l'Atlantique émettent hors profil À LA MÊME MINUTE dans deux bassins différents :
  une bonne réponse à 'ces anomalies sont-elles liées ?' doit le remarquer (coordination possible).
- L'écart azimut du Surcouf est vérifiable géométriquement (bearing radar→navire vs azimut enregistré).
- Jointures nécessaires : tracks × Radar_Sites (portée, position), tracks × Ports (port d'attache, distance).