# Fred demo script — Monday industrial review · Mecalys SA

Opening line to set the thread: "The Vektor range has lost margin every month since March, and
nobody agrees on why. We'll run the Monday industrial review with Fred: first check that we can
trust the agent, then interrogate the operations workbook, cross it with our procurement
procedure, and end on a supplier decision backed by evidence."

The star capability on display: **multi-tab Excel ingestion** — one workbook, seven
interdependent tabs, and questions whose answers exist in no single tab.

---

## Act 1 — Trust first (nothing to type)

Show the evaluation results on `dataset-industry-ops.json` (15 cases).
Open the trace of one imperfect case and unroll it in 30 seconds:
"A plausible, well-written answer that quietly counted 23 products instead of 25 — it dropped the
discontinued ones without saying so. A human reviewer would have waved it through. Only the
ground-truth evaluation caught it. That is why we evaluate before we trust."

---

## Act 2 — The Excel agent, live (one workbook, seven tabs)

**Q1 — warm-up (single tab)**
```
How many products do we have, by range, and how many are active?
```
Expected: 25 products — Vektor 7, Orion 6, Atlas 6, Pulsar 6; 23 active, VK-090 and AT-380
discontinued.

**Q2 — aggregation with a threshold**
```
Which parts are below their safety stock right now?
```
Expected: 14 parts; worst is AL-7043 at 260 on hand vs 720 safety stock — a class A housing.

**Q3 — the derivation trap (the answer is in no column)**
```
Do we have late purchase orders? I don't see any "late" status in the data.
```
Expected: 9 late POs, derived from due_date vs the as-of date; 5 of them on TechAlu Foundry.
Say it out loud: "No column says 'late'. The agent compared dates and statuses itself."

**Q4 — the star question (four tabs joined)**
```
Which parts are both below safety stock and only covered by a late order,
and which products does that put at risk?
```
Expected: 3 parts (AL-7043, BR-2204, CN-6120) → 15 active products at risk, including the entire
active Vektor range. Transition: "Every single Vektor product hangs on one casting from one
foundry. Let's see what our own rules say about that."

---

## Act 3 — Hybrid: data against policy (Excel + SOP + audit report)

**Q5 — RAG warm-up (document only)**
```
What does our procurement procedure require when a supplier's OTD drops below 85%?
```
Expected: §5.1 — corrective action plan within 15 working days; if the CAP deadline lapses,
restrict new orders and escalate.

**Q6 — the compliance verdict (everything at once)**
```
Is TechAlu Foundry compliant with our procurement procedure as of today?
```
Expected: no, on four grounds — OTD 71% (§5.1); CAP deadline 2026-06-15 lapsed with OTD still at
71%; single-source waiver expired 2026-05-31 (§4.2); 22 NCRs on AL-7043 in Q2, above the §7.2
quarterly threshold of ten. Emphasize: "The Suppliers tab says 'approved'. The verdict required
two PDFs and three tabs."

**Q7 — the consistency audit (optional, if time allows)**
```
Are there inconsistencies between our supplier data and what the procedure mandates?
```
Expected: Delta Polymers rated 74 — below the §5.3 suspension threshold — yet three open POs.

---

## Act 4 — The reveal: why Vektor is losing margin

**Q8 — the trend**
```
How has the Vektor gross margin evolved this year, compared to the other ranges?
```
Expected: stable ~34% through February, then −5.8 points to 28.3% in July; other ranges flat.

**Q9 — the root cause**
```
Why? Cross-check the finance data with the supplier documents.
```
Expected: the audit report records an 18% price increase on the Vektor housing effective
2026-03-01 — the exact inflection month — on a part present in every Vektor unit, compounded by
porosity scrap. Closing line: "Four questions, one workbook, two PDFs, one CSV. The Monday
industrial review used to take the morning; the argument is now on the screen, with sources."
