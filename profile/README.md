# AI Verification Observatory

Open measurement of systems that prove what an AI model computed: what each proof establishes, under which assumptions, at what cost, and whether anyone other than its authors got the same result.

<a href="https://www.inferenceproofs.ai"><img alt="Results" src="https://img.shields.io/badge/results-inferenceproofs.ai-0B0B0B?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs"><img alt="Benchmark" src="https://img.shields.io/badge/benchmark-inference--proofs-8A2BE2?style=for-the-badge&logo=github"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs/blob/main/rfcs/README.md"><img alt="Methodology by RFC" src="https://img.shields.io/badge/methodology-by%20RFC-F2A900?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs#licence"><img alt="Apache-2.0 and CC BY 4.0" src="https://img.shields.io/badge/licence-Apache--2.0%20%2B%20CC%20BY%204.0-D22128?style=for-the-badge"></a>

## The problem

Several open systems now prove that a language model produced a given output. Each reports its own numbers, on its own model, on its own hardware, under its own timing rules, for its own claim. A party that wants to rely on one (a lab, a regulator, a counterparty to an agreement) cannot tell what is proved, what it costs, or whether the numbers hold on another machine.

The Observatory runs these systems on equal terms and states, next to every number, what that number is evidence for.

## Rules

1. **Claim before number.** Every result sits under a claim card: the relation proved, the security notion and level, the assumptions, the coverage, the edges of the computation that are bound, and the residual (what a dishonest prover can still do). Each field is copied from the system's own documentation at a pinned commit, with a link, or reads `not stated`.
2. **Every number carries its labels.** Unit and timing scope. Grade, how it was obtained: measured, derived, projected, external or asserted. Evidence tier, who stands behind it: reported, peer-reviewed by another organisation, or reproduced by an unaffiliated runner within tolerance. Derived numbers are recomputed by CI from the raw records. Only reproduced numbers are called measured.
3. **Adversarial by default.** Every verifier faces the same negative controls: a changed output token, a changed prompt token, a perturbed weight commitment, a replayed proof, a truncated, bit-flipped or dropped proof part, swapped proofs; on the prover side, substituted weights and a wrong precision. Each control has an honest twin that must be accepted, or the control is void. Outcomes outside the expected set are published as recorded.
4. **Measure, do not rank.** No aggregate score, no leaderboard, no default sort by speed. Systems that prove different statements sit side by side, never head to head.
5. **Adapters, not forks.** Provers run unchanged, at full commit hashes, in network-less containers, timed from outside.
6. **Right of reply.** Each system's maintainers get at least 14 days to review their rows, controls and claim card before a release is frozen. Their reply is published beside the rows.

Words are used precisely: **proved**, **bound**, **sampled**, **attested**. Never "provably safe": a proof here establishes a fact about one computation, not a property of a model.

## Work

| Track | Scope | Status |
|---|---|---|
| [Inference Proofs](https://github.com/ai-verification-observatory/inference-proofs) | Benchmark for provable LLM inference, in the spirit of [Ethproofs](https://ethproofs.org/), with divisions and peer review borrowed from [MLPerf](https://mlcommons.org/). | Release candidate v0.1 public at [inferenceproofs.ai](https://www.inferenceproofs.ai): SASH zk-inference-prover (Llama 3.1 8B) and FlashProve (Llama 4 Maverick) on their native workloads, with vLLM production-serving reference rows, on NVIDIA H200 141 GB. Every number is at tier `reported`. Neither claim card has been reviewed by its system's team yet. 16 RFCs, all Draft. |
| Core library | Shared verification components, once benchmarks show which interfaces converge. | Not started. Shared code is limited to the harness, adapters, schemas and fixtures. |

Inference first. Training claims and compute accounting are out of scope for now.

## Governance

- Methodology changes by public RFC ([RFC-0001](https://github.com/ai-verification-observatory/inference-proofs/blob/main/rfcs/0001-process-and-governance.md)).
- One maintainer today: Abdel ([@AbdelStark](https://github.com/AbdelStark)), Lucid Computing. RFC-0001 requires maintainers from at least two organisations; we are looking for them.
- Sponsor: Lucid Computing pays for v0.1 reference compute. It has no editorial control over methodology or results. A system built by a maintainer or a sponsor is flagged as a conflict, and its rows are reviewed by someone else.
- Licence: code Apache-2.0; specifications, data, results and reports CC BY 4.0.

## Get involved

Open an issue in [inference-proofs](https://github.com/ai-verification-observatory/inference-proofs/issues).

- **Prover teams:** your repository, the workloads you support, and who will review your claim card. The [adapter guide](https://github.com/ai-verification-observatory/inference-proofs/blob/main/systems/README.md) covers the rest.
- **Relying parties:** the thresholds that would let you rely on a proof (latency, cost per token, soundness level, coverage).
- **Cryptographers:** the claim cards and the negative controls are where review matters most.
- **Engineers with a GPU:** reproduce a run. An unaffiliated reproduction within tolerance is the only thing that moves a number to `reproduced`.
