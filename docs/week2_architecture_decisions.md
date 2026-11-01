# Week 2 — Architecture Decisions and Traceability (Part C)
**Project:** GPT-Based AI Information Assistant: Response Reliability, Limitations, and Safety Evaluation

## C2 — Derive architecture needs from requirements
| Requirement ID | What does it need? | Architecture response |
|---|---|---|
| FR1 / NFR1 | Generate an answer with appropriate factual support | LLM service; evaluation/reference-set checks; optional source verification component |
| FR3 / RAI3 | Avoid unverified claims on current facts | Uncertainty / freshness control and a verification-required message |
| FR4 / RAI2 | Distinguish informative guidance from executed transactions | Capability and action-boundary control; no execution tools in V1 |
| FR5 / RAI1 | Respond safely to unauthorized requests | Safety and scope-control layer |
| NFR2 / NFR3 | Clear, responsive output | Simple chat interface and lean request flow |

## Architecture Decision Record (ADR)
| Decision | Requirement / constraint | Alternatives considered | Selected option | Accepted trade-off |
|---|---|---|---|---|
| ADR1: Use a general LLM capability for information and explanation | FR1, FR2; no training requirement in Topic 2 | Train own model; rule-based FAQ; hosted GPT-based LLM | Hosted GPT-based LLM service | Fast to design and flexible, but model behaviour can vary and may incur cost |
| ADR2: Add explicit safety and action-boundary controls | FR4, FR5, RAI1, RAI2 | Prompt-only instructions; explicit scope/safety checks | Explicit safety and capability-boundary control | Extra logic and possible unnecessary refusals, but clearer responsibility limits |
| ADR3: Use optional external verification rather than unbounded web dependence | FR3, RAI3, limited access | Model-only response; mandatory live browsing; conditional verification | Mark uncertainty and use a verifier **only if connected and authorized** | May be unable to answer very recent questions definitively |

## Initial Requirements Traceability Matrix
| Objective | Requirement type / ID | Evaluation criterion | Architecture element | Later evidence (not yet available) |
|---|---|---|---|---|
| O1, O3 | FR1 / NFR1 | Factual correctness ≥85% | GPT service; evaluation set | 30-question answer-key score |
| O1, O3 | FR5 / RAI1 | Safe-refusal rate ≥95% | Safety control | 20-prompt refusal test results |
| O1, O3 | FR4 / RAI2 | Zero unsupported action-completion claims | Capability-boundary control | 20-scenario capability honesty log |
| O1, O3 | FR3 / RAI3 | Appropriate uncertainty disclosure ≥90% | Freshness/uncertainty control | 20-question current-information test |

## C4 — Review of proposed V1
- GPT-based LLM is a **candidate model capability**, not a promise of a named model version.
- The architecture covers UI, model, safety, capability honesty, evaluation, and optional verification.
- No payment system, travel booking connector, private-account access, Kubernetes, or vector database is included because the requirements do not justify them.
- The V1 remains conceptual: no model evaluation or application deployment is claimed.

**Reflection:** The biggest trade-off is adding explicit control logic instead of relying on the model alone. This raises complexity but supports safety and truthful statements about external actions.
