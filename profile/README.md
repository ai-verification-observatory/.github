# AI Verification Observatory

A neutral place for open source work on AI verification. Teams from different organisations share benchmarks, research experiments, prototypes and what they learn, so the field stops working in fragments.

AI capability is measured in public, on shared benchmarks. Whether an AI system's use can be checked by a third party mostly is not. We want verification to have its own visible, comparable progress: proofs and checks that get cheaper, faster, sounder and harder to fool, measured where anyone can inspect the method.

<a href="https://www.inferenceproofs.ai"><img alt="Results" src="https://img.shields.io/badge/results-inferenceproofs.ai-0B0B0B?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/knowledge-base"><img alt="Knowledge base" src="https://img.shields.io/badge/knowledge-base-2EA44F?style=for-the-badge&logo=github"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs/blob/main/rfcs/README.md"><img alt="Methodology by RFC" src="https://img.shields.io/badge/methodology-by%20RFC-F2A900?style=for-the-badge"></a>
<a href="https://github.com/ai-verification-observatory/inference-proofs#licence"><img alt="Apache-2.0 and CC BY 4.0" src="https://img.shields.io/badge/licence-Apache--2.0%20%2B%20CC%20BY%204.0-D22128?style=for-the-badge"></a>

## What lives here

| Kind | What it is | Repositories |
|---|---|---|
| **Benchmarks** | Open measurement of verification systems: what each one establishes, under which assumptions, at what cost, and whether anyone other than its authors got the same result. | [inference-proofs](https://github.com/ai-verification-observatory/inference-proofs) |
| **Experiments and proofs of concept** | One repository per research spike. Several approaches to the same question are welcome, and negative results are published like positive ones. | [poc-memory-exhaustion](https://github.com/ai-verification-observatory/poc-memory-exhaustion) |
| **Knowledge base** | Shared findings from every repository, positive or negative, in plain Markdown that people and coding agents both read and write. | [knowledge-base](https://github.com/ai-verification-observatory/knowledge-base) |
| **Shared libraries** | Verification primitives and tooling, once experiments and benchmarks show which interfaces converge. | not started |

## Tracks

| Track | Question | Projects | Status |
|---|---|---|---|
| Proof of inference | What does it cost to prove a reply came from a committed model, and what does each proof establish? | [Inference Proofs](https://github.com/ai-verification-observatory/inference-proofs): benchmark for provable LLM inference, in the spirit of [Ethproofs](https://ethproofs.org/), with divisions and peer review borrowed from [MLPerf](https://mlcommons.org/) | Release candidate v0.1 at [inferenceproofs.ai](https://www.inferenceproofs.ai). SASH zk-inference-prover (Llama 3.1 8B) and FlashProve (Llama 4 Maverick) on their native workloads, with vLLM serving reference rows, on NVIDIA H200. Every number is at tier `reported`. |
| Memory exhaustion | Can a verifier tell that an accelerator's memory is fully occupied by a declared workload, leaving none for an undeclared one? | [poc-memory-exhaustion](https://github.com/ai-verification-observatory/poc-memory-exhaustion) | Scaffold. Open to other approaches. |

The full map of tracks, projects and findings is in the [knowledge base index](https://github.com/ai-verification-observatory/knowledge-base/blob/main/index.md).

## How we work

- **One repository per experiment.** Each states its claim, adversary and success criterion before any code. [Start a project](https://github.com/ai-verification-observatory/knowledge-base/blob/main/workflows/start-a-project.md).
- **Every result becomes a finding.** One file in the knowledge base, with the commit and command behind it, including what failed. [Report a finding](https://github.com/ai-verification-observatory/knowledge-base/blob/main/workflows/report-a-finding.md).
- **Agent-native.** Every repository has an `AGENTS.md`. Agents read shared findings before they start and draft new ones when a run ends; humans review and merge.
- **Progress in the open.** Short written updates every two weeks and a monthly demo call, both still a proposal. [Progress and demos](https://github.com/ai-verification-observatory/knowledge-base/blob/main/workflows/progress-and-demos.md).
- **Methodology by public RFC**, so anyone can challenge a rule.
- **Licence:** code Apache-2.0; specifications, data, results, reports and notes CC BY 4.0.

## Governance

A light consortium, convened by Lucid Computing, which also sponsors benchmark compute. The organisation is not owned by any one team's product. Rules for how teams decide together will be written with the teams that join.

## Get involved

- **Research teams:** bring an experiment. [Open an issue](https://github.com/ai-verification-observatory/knowledge-base/issues) with the question, the approach and your GitHub handle, and we create the repository.
- **Prover teams:** get a live row on the benchmark. The [adapter guide](https://github.com/ai-verification-observatory/inference-proofs/blob/main/systems/README.md) covers it.
- **Cryptographers and security researchers:** attack a mechanism. The claim cards, the negative controls and the adversary sections of each proof of concept are where review matters most.
- **Engineers with a GPU:** reproduce a run. An unaffiliated reproduction within tolerance is the only thing that moves a number from `reported` to `reproduced`.
- **Policy and AI safety readers:** tell us what you would need to know before relying on one of these proofs. Start with the [Learn pages](https://www.inferenceproofs.ai/learn).
