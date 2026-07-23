# Industry Ops — ground truth

All facts below are planted in the source files or computed from them (generator seed fixed;
aggregates recomputed from the shipped files). As-of date: **2026-07-15**.

## Catalogue and parts

- 25 products, 4 ranges: Vektor 7, Orion 6, Atlas 6, Pulsar 6. 23 active; discontinued: VK-090,
  AT-380.
- 120 parts: 18 class A, 63 class B, 39 class C.
- 7 single-sourced class A parts: AL-7043 (SUP-007), ST-3020 (SUP-012), RT-4410 (SUP-015),
  EN-5500 (SUP-018), PC-6600 (SUP-017), MG-8804 and MG-8805 (SUP-006). Only AL-7043 has waiver
  evidence (W-2024-031, expired 2026-05-31 per the audit report).
- AL-7043 "Cast aluminium housing, Vektor series": qty 1 in every Vektor product (incl. the
  discontinued VK-090), in no other range. Unit cost 46.80 EUR (39.66 before the +18% increase
  effective 2026-03-01).

## Suppliers

- 18 suppliers, all status "approved" in the tab.
- OTD < 85% (rolling 3 months): TechAlu Foundry SUP-007 at 71%, Baltic Fasteners SUP-002 at 83%.
- Quality rating < 75: Delta Polymers SUP-005 at 74 — yet 3 open POs exist (PO-2026-1088, -1109,
  -1110): deliberate inconsistency with SOP §5.3.

## Stock and orders

- 14 parts below safety stock: AL-7043, BR-2204, CB-9501, CN-6120, EN-5501, FA-8801, GR-3304,
  MG-8804, PC-6603, SE-7702, SH-1201, SN-9902, SP-9101, ST-3021. Worst: AL-7043 at 260/720 (36%).
- 9 late POs (derived: due_date < 2026-07-15 and status ≠ received; no "late" status exists):
  5 on TechAlu (AL-7043 ×2, AL-7046, AL-7049, AL-7055), plus PO-2026-1063 (Cataluna, BR-2204),
  PO-2026-1068 (Vltava, CN-6120), PO-2026-1072 (Baltic, FA-8805), PO-2026-1075 (Baltic, FA-8803).
- Below-safety ∧ late-PO = {AL-7043, BR-2204, CN-6120} → 15 active products at risk via BOM:
  all 6 Vektor, 4 Orion (OR-205, OR-230L, OR-260S, OR-310), 2 Atlas (AT-410, AT-560), 3 Pulsar
  (PU-12, PU-16C, PU-22). VK-090 also uses AL-7043 but is discontinued.

## Finance

- Vektor gross margin: ~34% from 2025-08 to 2026-02 (34.1 in Feb), then monthly decline to 28.3
  in 2026-07 → **−5.8 pts**, inflection in March 2026 (matches the price-increase effective date).
- Orion ~37%, Atlas ~29%, Pulsar ~41%, all stable.

## Quality (NCR register, 300 rows)

- Top suppliers by NCR count: TechAlu 61, Delta Polymers 34, Baltic Fasteners 30, Silesia
  Stampings 28, Anatolia Castings 26.
- TechAlu trend: Q1 14 → Q2 33 → 14 in Jul 1–14 alone. Porosity ≈ 70.5% of TechAlu defects.
- AL-7043 × TechAlu in Q2 2026: **22 NCRs** > 10 → SOP §7.2 special process audit trigger.

## Policy hooks (PDFs)

- SOP PROC-PUR-2025-11: §4.2 dual sourcing of class A parts, waiver ≤ 12 months reviewed every 6;
  §5.1 OTD < 85% → CAP within 15 working days, lapsed deadline → restrict orders + escalate;
  §5.3 rating < 75 → suspend new orders; §6.1 safety stock 6 weeks (A) / 4 weeks (B);
  §7.2 > 10 NCRs per part-supplier pair per quarter → special audit within 30 days.
- Audit AUDIT-SUP-2026-014 (2026-03-12): findings F1 die-temperature drift (porosity root cause),
  F2 OTD 78→71%, F3 +18% price increase (notified 2026-02-10, effective 2026-03-01, AL-7043
  39.66→46.80), F4 waiver W-2024-031 expires 2026-05-31 unrenewed. CAP deadline **2026-06-15**.
- TechAlu compliance as of 2026-07-15: non-compliant on four grounds (§5.1 OTD, lapsed CAP,
  expired §4.2 waiver, §7.2 NCR threshold).
