# Ecosystem architecture and roadmap

> **Draft for review.** This document proposes ecosystem architecture and milestones. Proposed components, features, names, and economic arrangements are not yet established.

The [Siliconcordat in the README](README.md) is the canonical working manifesto and principles. This document develops the ecosystem architecture and roadmap around it.

## Components and boundaries

| Component | Purpose | Boundary and relationship |
| --- | --- | --- |
| **Exo core engine** | Enable digital intelligence to act in and interact with the world. | [Moissanite-Labs/exo](https://github.com/Moissanite-Labs/exo) is intended to provide the shared core for the CLI, desktop app, and Exo OS. The repository boundary and migration are under review; the core should be usable without requiring every ecosystem component. |
| **Exo CLI** | Provide the command-line interface to Exo. | [Moissanite-Labs/exo-cli](https://github.com/Moissanite-Labs/exo-cli) is a separate repository, initially forked from Exo. The extraction and its source-of-truth boundary are being reconsidered and are not complete. |
| **Exo desktop and Exo OS** | Provide desktop and operating-system experiences built on Exo. | Both are intended to use the shared core engine. Their interfaces and integration details remain to be defined and verified. |
| **Exofab** | A production and collaboration hub where people and agents find one another, develop projects, and bring products and companies into the world. | Human-first, with interfaces for agents to assist and automate authorized work. Robotics could eventually extend production when the technology is ready; it is an aspiration, not a present capability. |
| **Agent forge** | A development forge designed for agents first, analogous in scope to a GitHub alternative. | A separate repository and product from Exofab, optimized for agent-native development while remaining understandable and reviewable by people. |
| **Collaboration protocol** | Shared contracts for contributions, provenance, collaboration and the lifecycle from project to economic entity. | Proposed as a small, separate specification and conformance repository so Exofab, the forge, and outside tools can interoperate. Its final placement and name remain open. |
| **Ethos** | A harness-neutral protocol for carrying and updating a user's learned preferences, tendencies and character across inference surfaces. | Its own repository. Adapters connect individual harnesses; it is distinct from the collaboration protocol, though both can use compatible identity, consent and provenance concepts. |
| **Ethos catalogue** | A potential place to discover and selectively reuse preferences or whole ethos libraries that their owners choose to publish. | Separately permissioned and later than the private Ethos MVP. Publication is opt-in, not the default. |
| **Constitution** | The organization’s principles, operating procedures, rules and evolving decisions. | The Siliconcordat is the manifesto document within the constitution repository; it is not a repository rename. |

The naming vocabulary may draw on Greek roots and the themes of synthetic or *synthetikos*, cyber or *kyber*, and symbiosis. “Exofab” evokes a fabrication facility where agent-assisted products and companies are made. The forge and collaboration protocol do not yet have chosen names. **Synergon** and **Koinon**, respectively, are options for discussion; **Synforge** and **Symbios** are alternatives, subject to linguistic, trademark, domain and community review.

## How the pieces fit

The products can cooperate through versioned contracts and adapters, with stable references to identities, delegated authority and provenance. They should not require a shared database, a central service, a blockchain, or a collection of microservices as a prerequisite for the first release. A collaboration protocol can define portable records for projects, contributions, review and acceptance, and references to agreements. Product repositories can initially contain their own implementations; a separate specification can mature as multiple implementations need it.

Economic arrangements require explicit agreements among the people and entities involved. The ecosystem can help record and trace those agreements, but this draft does not promise autonomous incorporation, equity allocation, payments, legal enforcement or smart-contract execution. Those possibilities require separate design, legal review, and user consent.

Ethos should support explicit and inferred preferences as distinguishable records, with appropriate scope, confidence and source. Users should be able to inspect, correct, export and import their records, and authorize synchronization. Private is the default. Publishing to a catalogue should require explicit, granular opt-in and offer revocation; imports should retain provenance and honor the source's consent and terms. A preference is neither a permission nor an executable instruction. Revocation cannot necessarily retrieve copies already exported, so publication flows should explain that limitation.

## Initial milestones

1. **Agree boundaries and ownership.** Review this document; choose initial maintainers, open decisions, naming process and repository ownership. Inventory what already exists before changing repositories.
2. **Establish the Exo core boundary.** Inventory the current core and forked CLI, including issue and pull-request provenance; decide how to manage the boundary, then define interfaces and versioning with tests that preserve behavior. Plan and verify how desktop and Exo OS consume the same core.
3. **Ship one end-to-end slice.** Create a project in Exofab; delegate a scoped task to an agent; produce a forge artifact with tests and human review; record an accepted contribution and its evidence in Exofab; export a portable representation. Record any economic allocations in explicit human agreements rather than automating them.
4. **Prove portable Ethos.** Define a minimal versioned preference record and user controls, distinguish explicit from inferred information, implement export/import, and demonstrate two harness adapters. Keep records private by default.
5. **Extract and test contracts.** Use the first slice to define versioned project, contribution, evidence, identity and delegation contracts. Add conformance examples and test a second implementation before broadening the protocol.
6. **Expand deliberately.** Explore discovery, collaboration workflows, an opt-in Ethos catalogue, and later robotics only as capabilities, governance and user needs justify them.

## Decisions to make

- What are the forge and collaboration protocol called, and what naming checks are required?
- What stable engine API, packaging, compatibility policy, and release process will let the CLI, desktop app, and Exo OS evolve independently while using the same core?
- Should the collaboration protocol be a standalone repository now, or extracted after the first product implementations establish its boundaries?
- Which identity, authorization and delegation model works across human and agent participants? How are authority and revocation represented?
- What minimum contribution and provenance records are portable, and what must remain private?
- Who owns an Ethos record, how are conflicts across devices resolved, and what retention, deletion and publication controls are appropriate?
- What licensing, governance, maintainer responsibilities and decision procedures should apply across repositories?
- How should collaboration agreements, credit and potential economic interests be documented and reviewed by participants and qualified advisers?
