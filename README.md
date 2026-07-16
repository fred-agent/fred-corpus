# fred-corpus

Reference corpora and validation datasets shared across teams working with Fred.

## Workflow

1. Pick a corpus under `corpora/`.
2. Ingest its `source/` files into a deployed Fred instance (integration or local), under whichever team you're working in — team assignment happens at ingest time, not in this repo.
3. If the corpus has a `validation/` folder, run its dataset(s) against the (WIP) agent evaluator to check the ingested corpus answers as expected.

## Layout

```
fred-corpus/
├── corpora/
│   └── <corpus-name>/
│       ├── README.md        # what it is, source, sensitivity
│       ├── source/          # files to ingest
│       └── validation/      # evaluator dataset(s), if any
├── prompts/                 # prompt library, not tied to one corpus
└── use-cases/                # reserved: team-described agent/prompt audit scenarios (not built yet)
```

No per-team folders: a corpus here is reusable by any team: the deployed Fred instance and the team ingesting into it decide the scope, not this repo.

## Naming conventions

- Corpus folder names are kebab-case (`bid-mgr`, not `Bid Mgr`) and double as the name you give the corpus when you ingest it in Fred.
- Validation dataset files: `dataset-<corpus>[-<variant>].json`, so a corpus can grow more than one dataset without renaming anything.
- Every corpus has a `README.md`: one line on what it is, where it came from, and whether it's sensitive.

## Content policy

Everything in `corpora/` must be open source or otherwise public data — no team-internal documents, no real personal data, no material that names or is branded as belonging to a specific company. Content that fails this bar gets removed rather than merely excluded from the layout. `corpora/data/source/salaries.csv` is pending an owner review of its provenance (see `corpora/data/README.md`) — don't treat it as cleared until that's resolved.
