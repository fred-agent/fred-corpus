# Technical Policy

Long normative documents (numbered requirements and recommendations) for testing policy-oriented
RAG agents: multi-section retrieval, many chunks per document, citation by page, and
answers that must separate what the corpus says from what is inferred.

**Source**: public, see below
**Sensitive data**: no
**Validation datasets**: `validation/dataset-technical-policy.json` (17 cases, `complete`)

## Source files

- `source/anssi-guide-hygiene-informatique-v2.0.pdf` — ANSSI, *Guide d'hygiène informatique :
  renforcer la sécurité de son système d'information en 42 mesures*, version 2.0, September 2017.
  French, 72 PDF pages, 42 measures in 9 chapters, each measure graded "standard" or "renforcé".
  Downloaded on 2026-10-10 from
  <https://messervices.cyber.gouv.fr/documents-guides/guide_hygiene_informatique_anssi.pdf>
  (SHA-256 `e95cb1cd6328d552dab56ade65c611b899f302001a5b256f89109c4f952e0591`).
  Licence Ouverte / Open Licence (Etalab V1), stated on the last page.

## Page numbers

The guide's printed page numbers are offset from the PDF's: printed page N is PDF page N + 2
(the cover and the foreword come first). Check which numbering an agent cites before scoring it.

## Validation dataset

`validation/dataset-technical-policy.json` is an evaluation document for the agent evaluator. Each
case is tagged with its kind and the measures it draws on (`mesure-N`):

- `precise` — one measure answers it.
- `cross-chapter` — the answer is spread over five to seven measures on different pages; an agent
  that keeps a single passage per document cannot cover it.
- `level` — the "standard" versus "renforcé" distinction.
- `english` — an English question over this French corpus.
- `out-of-corpus` — the guide does not answer it; the expected answer says so (`inference`: related
  measures may be cited, labelled as inference).

Expected answers state facts only, without page numbers: Contextual Recall compares them with the
retrieved passages. To check an agent's citations, the measures used start on these PDF pages:

| Measures | PDF page | Measures | PDF page | Measures | PDF page |
|---|---|---|---|---|---|
| foreword (method) | 5 | 13 | 21 | 29 | 41 |
| 1 | 7 | 14 | 23 | 32 | 45 |
| 2 | 8 | 17 | 26 | 33 | 46 |
| 3 | 9 | 20 | 30 | 34 | 48 |
| 8 | 16 | 24 | 34–35 | 36 | 51 |
| 10 | 18 | 25 | 36 | 37 | 53 |
| 11 | 19 | 26 | 37 | 40 | 56 |
| 12 | 20 | 27, 28 | 39, 40 | 42 | 60 |
