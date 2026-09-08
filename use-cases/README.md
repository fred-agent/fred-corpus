# Use cases

Versioned scenarios for auditing what an agent or prompt actually does. A use case can span more
than one knowledge base, so it sits alongside `corpora/` and `prompts/` rather than inside either.

Each folder contains a `README.md`, a canonical prompt and an evaluation rubric. Source documents
stay in `corpora/`; answer keys and validation material must never be ingested with them.

Current scenario:

- `reliable-tender-work-completion/` — multi-step tender analysis, real Workspace files and an
  explicit human decision point.
