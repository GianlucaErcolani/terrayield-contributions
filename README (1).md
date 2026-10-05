# TerraYield-2 — ML Dataset Readiness

**Gianluca Ercolani · Omdena contributor · Data quality, ML readiness and technical documentation**

This case study describes my contribution to the Gold Dataset ML intake readiness package in TerraYield-2. I owned the consolidated assessment document used to support Sprint 3 benchmark planning, bringing together four contributors’ reviews into one traceable reference.

**Contribution evidence:** [Pull request #49](https://github.com/OmdenaAI/TerraYield-2/pull/49), approved by Jash Thakkar and merged into `main` on August 28, 2026, following five author commits and a requested revision.

## The problem

The team needed to determine whether a candidate dataset combining agricultural, satellite, weather and commodity information could support crop-yield and land-use benchmarks. Populated columns alone did not establish fitness for modeling: label availability, temporal grain, invalid feature values, evaluation leakage and release traceability all affected the decision.

## My contribution

I authored and iteratively revised `docs/benchmarks/gold_dataset_ml_intake_readiness_v1.md` for task S2-21-ML-05. I:

- Consolidated four upstream deliverables covering benchmark fitness, modeling blockers, readiness classification and Data Engineering follow-up actions.
- Reconciled differences between the source assessments, including label-row versus independent-observation counts, weather aggregation interpretation and follow-up action counts.
- Documented benchmark-specific decisions, safeguards and dependencies instead of presenting a single unqualified readiness claim.
- Connected findings to prioritized Data Engineering actions and explicit acceptance criteria.
- Responded to reviewer feedback and completed the document’s implementation checklist before approval and merge.

## Technical issues captured in the assessment

| Issue | Documented implication |
|---|---|
| Features organized in 16-day windows, with annual/seasonal yield targets | Require deterministic seasonal aggregation and verification of unique modeling units; repeated rows must not be counted as independent labels. |
| Invalid or placeholder satellite features | Correct and revalidate affected fields or explicitly exclude them from the approved feature list. |
| Repeated features and temporal dependencies | Require grouped, temporally appropriate evaluation and causal filling rules to limit leakage. |
| Missing governed land-use labels | Defer the land-use benchmark or formally remove it from scope until suitable labels are available. |
| No confirmed fixed Gold release | Require a versioned artifact, immutable identifier and validation references before benchmark intake. |

## Outcome at the August 2026 review

| Scope | Consolidated decision |
|---|---|
| Unrestricted Gold Dataset intake | **Not ready.** Unresolved blockers and the absence of a confirmed fixed release prevented unrestricted use. |
| Restricted yield-only benchmark | **Conditionally ready.** Progress depended on seasonal aggregation, feature sanitization, fixed input versioning and leakage-safe evaluation. |
| Land-use benchmark | **Blocked.** Governed, spatially aligned labels were required. |

The package consolidated a team register of **30 issues: 21 blockers and 9 caveats**, and incorporated **27 Data Engineering follow-up actions** from the reconciled upstream action register. These counts describe shared assessment inputs, not findings independently discovered by me.

The verified delivery outcome was an **approved, merged assessment document**. This contribution did not include model training, pipeline implementation or measured predictive-performance improvements. The decisions above describe the reviewed snapshot, not the project’s later or current status.

## Collaboration and attribution

The package incorporated benchmark-fitness work by Nada Amr, the blocker/caveat register by Segun Odusina, readiness classification by Rena Abbasova and Data Engineering follow-up work by Fatima Athar. My responsibility was consolidation, reconciliation, documentation and delivery of the ML-05 package. Jash Thakkar reviewed and approved the pull request.

## Evidence and access

- [PR #49 — contribution, review and merge history](https://github.com/OmdenaAI/TerraYield-2/pull/49)
- [PR #49 — submitted document changes](https://github.com/OmdenaAI/TerraYield-2/pull/49/files)

Repository access may be required to view the evidence. The supplied document snapshot still says approval was pending; the subsequent PR discussion records approval and merge on August 28. This portfolio summary does not reproduce the underlying datasets or internal source documents.
