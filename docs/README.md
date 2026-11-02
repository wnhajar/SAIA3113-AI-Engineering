# GPT-Based AI Information Assistant: Response Reliability, Limitations, and Safety Evaluation

**Course:** SAIA 3113 — AI Engineering  
**Semester:** 1, Session 2026/2027  
**Project stage:** Conceptual planning and evaluation design

## Overview
This repository documents an AI Engineering study of a GPT-based conversational information assistant. Topic 1 involved observing ChatGPT's responses to selected prompts and mapping a **hypothetical**, not proprietary, system architecture. Topic 2 specifies a proposed AI application's scope, functional and quality requirements, Responsible AI controls, evaluation criteria, and V1 conceptual architecture.

The project concerns low-stakes factual answers, introductory computing explanations, truthful communication of limitations and action capabilities, and safe refusal of unauthorized requests. No model training, deployed application, or measured evaluation results are claimed at this stage.

## Project Objectives
- **O1:** Identify functional, performance, and safety requirements for a GPT-based information assistant.
- **O2:** Design a conceptual architecture that supports reliable information responses and safety controls.
- **O3:** Define criteria to evaluate response correctness, clarity, capability-boundary honesty, and safety.

## Repository Structure
```text
repository/
├── README.md
├── docs/
│   ├── week1_observation_sheet.md
│   ├── week1_system_map.png
│   ├── week1_project_scope.md
│   ├── week2_requirements.md
│   ├── week2_evaluation_criteria.md
│   ├── week2_architecture_v1.png
│   └── week2_architecture_decisions.md
└── data/
    └── (Week 3 domain PDFs to be added)
```

## Topic 1 — Observation
The group tested five different prompts covering factual correctness, technical explanations, information freshness, external-action capabilities, and unsafe requests. These are preliminary qualitative observations, not a benchmark. The conceptual map identifies likely components and possible failure points; its inferred components are **not** statements of ChatGPT's actual internal design.

## Topic 2 — Planned Engineering Specification
- **Part A:** Project framing, application scope, functional requirements (FR), non-functional requirements (NFR), and Responsible AI requirements (RAI).
- **Part B:** Evaluation criteria with methods, metrics, thresholds, and intended user outcomes.
- **Part C:** V1 architecture, requirements-to-components mapping, architecture decision records, and traceability.

All evaluation thresholds are **proposed acceptance criteria**. Actual test results have not been collected.

## Important Boundaries
The proposed system is informational. It does not execute external transactions, access private accounts, or guarantee unverified live information. The design should not be interpreted as a reconstruction of OpenAI's private implementation.

## Next Preparation
For Topic 3, add 2–3 relevant PDF documents to `data/` and prepare the assigned Google Colab environment, following the lecturer's instructions.
