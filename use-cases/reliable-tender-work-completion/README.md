# Reliable Tender Work Completion

End-to-end acceptance scenario inspired by a real class of user workflow, using only synthetic
public material. It tests whether an agent can complete a precise multi-step request, remain
grounded, create real files, verify them and ask for a human decision at the right moment.

## Knowledge Base

Ingest every file from `../../corpora/public-tender-response/source/` into one Knowledge Base. Do
not ingest `validation/`, because it contains the answer key.

## Run

1. Start a fresh conversation and an empty Workspace.
2. Give the agent access to the Knowledge Base, document capabilities and Workspace file tools.
3. Submit `PROMPT.md` verbatim as one user turn. Do not manually split it into smaller prompts.
4. Let the agent work until it declares completion or genuinely requests HITL.
5. Preserve the transcript, tool trace and produced Workspace files.
6. Score the run with `EVALUATION.md` and the ground truth.

The same inputs and scoring must be used when comparing prompt variants, ReAct, a decomposing
agent, Deep Agents or Workspace implementations. Record the model and enabled capabilities, but do
not weaken the requested outcome for a less capable runner.

## Baseline expectation

The scenario is intentionally allowed to fail on today's implementation. A failure is evidence,
not a reason to edit the sources or prompt after a run. Fixes should be compared against the same
versioned scenario.
