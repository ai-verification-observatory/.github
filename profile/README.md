# AI Verification Observatory

An effort to foster more open source collaboration in the AI verification ecosystem. We all share the same mission, let's join forces to make sure we accelerate the research and adoption of the verification primitives. 

- Open measurement of systems that prove what an AI model computed: what each proof establishes, under which assumptions, at what cost, and whether anyone other than its authors got the same result.
- Research experiments
- Prototype developments
- Libraries, shared primitives and tooling

<a href="https://www.inferenceproofs.ai"><img alt="Results" src="https://img.shields.io/badge/results-inferenceproofs.ai-0B0B0B?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs"><img alt="Benchmark" src="https://img.shields.io/badge/benchmark-inference--proofs-8A2BE2?style=for-the-badge&logo=github"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs/blob/main/rfcs/README.md"><img alt="Methodology by RFC" src="https://img.shields.io/badge/methodology-by%20RFC-F2A900?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs#licence"><img alt="Apache-2.0 and CC BY 4.0" src="https://img.shields.io/badge/licence-Apache--2.0%20%2B%20CC%20BY%204.0-D22128?style=for-the-badge"></a>

## Work

| Track | Scope | Status |
|---|---|---|
| [Inference Proofs](https://github.com/ai-verification-observatory/inference-proofs) | Benchmark for provable LLM inference, in the spirit of [Ethproofs](https://ethproofs.org/), with divisions and peer review borrowed from [MLPerf](https://mlcommons.org/). | Release candidate v0.1 public at [inferenceproofs.ai](https://www.inferenceproofs.ai): SASH zk-inference-prover (Llama 3.1 8B) and FlashProve (Llama 4 Maverick) on their native workloads, with vLLM production-serving reference rows, on NVIDIA H200 141 GB. Every number is at tier `reported`. Neither claim card has been reviewed by its system's team yet. 16 RFCs, all Draft. |
| Core library | Shared verification components, once benchmarks show which interfaces converge. | Not started. Shared code is limited to the harness, adapters, schemas and fixtures. |

Inference first. Training claims and compute accounting are out of scope for now.

## Governance

Work in progress. Will be defined as we onboard more teams to the effort and establish how we want to work together.

- Methodology changes by public RFC 
- Licence: code Apache-2.0; specifications, data, results and reports CC BY 4.0.

## Get involved

Open an issue in [inference-proofs](https://github.com/ai-verification-observatory/inference-proofs/issues).

- **Prover teams:** your repository, the workloads you support, and who will review your claim card. The [adapter guide](https://github.com/ai-verification-observatory/inference-proofs/blob/main/systems/README.md) covers the rest.
- **Relying parties:** the thresholds that would let you rely on a proof (latency, cost per token, soundness level, coverage).
- **Cryptographers:** the claim cards and the negative controls are where review matters most.
- **Engineers with a GPU:** reproduce a run. An unaffiliated reproduction within tolerance is the only thing that moves a number to `reproduced`.
