# Industry Ops

Synthetic manufacturing operations corpus for a fictional actuator maker (Mecalys SA): multi-tab
Excel ingestion, cross-tab joins, CSV aggregation, and hybrid data-vs-policy questions against two
PDF procedures.

**Source**: synthetic — fabricated products, parts, suppliers, stock, orders, finance and quality
records; no real company, product or individual is represented
**Sensitive data**: no
**Validation datasets**: `validation/dataset-industry-ops.json` (15 cases)

## Source files

- `source/mecalys-operations-2026.xlsx` — 7 interdependent tabs (Products, BOM, Parts, Suppliers,
  Stock, OpenOrders, Finance), as of 2026-07-15. All cells are literal values (no formulas), by
  design: this is an ingestion corpus, and formula cells read as empty to pipelines that consume
  cached values.
- `source/quality-incidents-2026.csv` — 300 non-conformity reports (NCR), 2026-01-02 to 2026-07-14
- `source/PROC-PUR-2025-11.pdf` — procurement, supplier management and inventory SOP (the policy
  side of the hybrid questions)
- `source/AUDIT-SUP-2026-014-TECHALU.pdf` — for-cause supplier audit report with a corrective
  action plan and deadlines

## The planted story

The Vektor range loses 5.8 margin points between February and July 2026. Root cause, spread across
the files and never stated in any of them: TechAlu Foundry (single source of the Vektor housing
AL-7043, expired waiver) raised prices 18% effective March, its OTD collapsed to 71%, its porosity
NCRs accelerated past the SOP escalation threshold, and its corrective action plan deadline of
2026-06-15 lapsed. `validation/GROUND-TRUTH-INDUSTRY.md` documents every planted fact.
