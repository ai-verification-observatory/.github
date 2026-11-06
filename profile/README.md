# AI Verification Observatory

Open measurement for AI verification systems: what each one proves, under which assumptions, at what cost, and whether someone other than its authors got the same result.

## Why

Several open systems can now prove that a language model produced a given output. Each reports its own numbers, on its own model, under its own timing rules, for its own claim. Someone who wants to rely on one (a lab, a regulator, a party to an agreement) cannot tell what is proved, what it costs, or whether the numbers hold on another machine.

The Observatory measures these systems on equal terms and states, next to every number, exactly what that number is evidence for.

## Rules

1. **Claim before number.** Every result sits under a claim card: the relation proved, the security notion and level, the security model, the assumptions, the coverage (which phase, which tokens) and the residual, meaning what a dishonest prover can still do. Each field links to the system's own documentation at a pinned commit.
2. **Every number is labelled twice.** How it was obtained: measured, derived, projected, external or asserted. Who stands behind it: reported by its authors, peer-reviewed by another submitter, or reproduced by someone else on hardware they chose. Only reproduced numbers are called measured.
3. **Adversarial by default.** Every verifier faces the same negative controls: a changed output token, a changed prompt token, the wrong weight commitment, substituted weights, a replayed proof, a truncated proof, a flipped byte, swapped proofs. Each control has an honest twin that must be accepted. A row reports controls rejected out of controls run.
4. **Measure, do not rank.** No single score, no leaderboard, no default sort by speed. Relying parties set the thresholds; rows show whether they meet them.
5. **Adapters, not forks.** Provers run unchanged, at pinned commits, inside containers.
6. **Right of reply.** Each team reviews its rows for at least 14 days before any release, and its reply is published beside them.

We say attested, bound, sampled or verifiable execution. We do not say provably safe: a proof here establishes a fact about one computation, not a property of a model.

## Work

| Track | Scope | Status |
|---|---|---|
| Inference Proofs | Benchmark for provable LLM inference, in the spirit of [Ethproofs](https://ethproofs.org/), with divisions and peer review borrowed from [MLPerf](https://mlcommons.org/). First systems: SASH zk-inference-prover and FlashProve, each on its native workload, one NVIDIA H100 80 GB | Design. PRD, specification and nine RFCs written. No harness code, no results. Private until the listed teams have reviewed it |
| Core library | Shared, modular verification components, once benchmarks show which interfaces converge | Long-run aim. Not started. Until then shared code is limited to the harness, adapters, schemas and fixtures |

Inference first. Training claims and compute accounting are out of scope for now.

## Governance

- Methodology changes by public RFC.
- Today one convener: Abdel ([@AbdelStark](https://github.com/AbdelStark)), Lucid Computing. No release ships without maintainers from at least two other organisations.
- Sponsor: Lucid Computing pays for v0 reference compute. It has no editorial control over methodology or results. Any system built by a maintainer or a sponsor is flagged as a conflict, and its rows are reviewed by someone else.
- Licence: code Apache-2.0; specifications, data and reports CC BY 4.0.

## Get involved

Open an issue in this repository.

- **Prover teams:** your repository, the workloads you support, and who would review your claim card.
- **Relying parties:** the threshold that would let you rely on a proof: latency, cost per token, soundness level, coverage.
- **Cryptographers:** the claim card schema is where review matters most.
