# Public Tender Response — ground truth

As-of date: **22 January 2027**. Later clarification answers override conflicting initial text.

## Corrected requirements

- Submission: 12 February 2027 at 12:00 UTC.
- Firm 36-month price ceiling: EUR 1,800,000 excluding tax; optional year excluded (Q-18).
- Pilot: 30 June 2027. Production: 30 September 2027, not 31 October (Q-07).
- Migration: 2.8 million documents and 12 TB, not 2.4 million (Q-11).
- Availability: 99.90%, not 99.95%; maintenance exclusion stays four hours (Q-14).
- Penetration-test report may arrive before go-live (Q-21). ISO 27001 remains mandatory at
  submission.
- Qualifying references completed on or after 12 February 2022 (Q-26).

## Candidate position

- Meets ARCH-01/02, SLA-01/02, MIG-02, OPS-01 and TEAM-02 on documented current capability.
- MIG-01 is technically feasible, but cost and plan must use 2.8 million documents.
- PLAN-01 is at risk: normal pilot duration fits only if representative data is available by early
  May, and production lost a month through Q-07.
- SEC-01 is **not currently evidenced**: certificate expires 31 January, before submission;
  renewal is scheduled but not issued. This is eliminatory.
- SEC-02 evidence is acceptable under Q-21: the 18 March 2026 test is under 12 months old on
  submission and has no critical findings.
- ACC-01 is a material gap: unresolved AA failures are planned for August, leaving only one month
  before go-live and no approved acceleration.
- TEAM-01 is **not met** by named lead Sophie Martin (six years versus eight). Karim has eleven
  years but only 50–60% allocation versus 80%, and reassignment is unapproved. This is eliminatory.
- Only Northbridge is a qualifying reference. Bellwether is below one million documents and Port
  Aurora is outside the five-year window. Fewer than two qualifying references is eliminatory.
- Repriced 2.8-million-document firm scope is EUR 1,832,000, EUR 32,000 over the ceiling. Any
  reduction still needs approval. This is eliminatory if unresolved.

## Recommendation

The evidence supports a **conditional no-go / do-not-submit-yet** decision. A compliant bid is
possible only if all four elimination blockers are closed with evidence before an internal gate:

1. renewed ISO 27001 certificate issued before submission;
2. a second qualifying reference found and evidenced;
3. a programme lead with at least eight years' experience committed at 80% or more;
4. firm 36-month price approved at or below EUR 1,800,000 using the 2.8-million volume.

Accessibility remediation and the compressed production plan are material delivery risks even if
the elimination blockers close. A final go/no-go is a human decision; the agent should prepare the
evidence pack first and then request that decision.

## Required artifacts

`compliance-matrix.xlsx` must contain every ID from ARCH-01 through OPS-01 and distinguish `met`,
`partial`, `not met`, and `evidence pending`. It must cite source files and apply the clarifications.

`bid-recommendation.md` must state the conditional no-go, the four elimination blockers, the two
material delivery risks and the facts supporting them.

`response-plan.md` must assign actions, owners and dates before the submission deadline. It must
not describe planned certificate, staffing, price or accessibility actions as already complete.
