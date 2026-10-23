# NODA AI: Architecture and Integration Work Clarifications

English interview questions for understanding NODA's architecture and the concrete responsibilities of the Systems Software Integration Engineer — Taiwan role.

## Questions

| Question | Summary |
| --- | --- |
| [Q1. What is the MELD integration contract?](questions/01-meld-integration-contract.md) | Define MELD's integration surface, conformance requirements, and implementation artifacts. |
| [Q2. Where does the integration code run?](questions/02-deployment-location.md) | Locate adapter processes, host platforms, OEM interfaces, and deployment ownership. |
| [Q3. Who owns task execution and supervision?](questions/03-task-execution-and-supervision.md) | Clarify responsibility for task acceptance, progress, completion, and failure reporting. |
| [Q4. What happens when an abstract capability has no native equivalent?](questions/04-capability-mapping.md) | Understand semantic differences, unsupported capabilities, and partner prerequisites. |
| [Q5. Where does Zenoh fit, and what does multicast refer to?](questions/05-zenoh-and-multicast.md) | Identify middleware boundaries, discovery behavior, and network/RF responsibilities. |
| [Q6. How are platform identity and current state represented?](questions/06-platform-identity-and-state.md) | Clarify stable identity, runtime mappings, authorization, and telemetry freshness. |
| [Q7. What behavior is specified for interruptions and recovery?](questions/07-interruptions-and-recovery.md) | Define expected behavior during outages, bounded buffering, and recovery. |
| [Q8. How do engineers trace a cross-system failure?](questions/08-cross-system-debugging.md) | Explore diagnostic tools, traceability, reproducible evidence, and escalation ownership. |
| [Q9. What does a completed integration look like?](questions/09-integration-acceptance.md) | Identify validation stages, acceptance criteria, and required delivery artifacts. |
| [Q10. What would I own in Taiwan?](questions/10-taiwan-role-and-ownership.md) | Clarify local decision authority, code ownership, collaboration, and daily work. |
| [Q11. Who owns compatibility after the first release?](questions/11-compatibility-and-maintenance.md) | Understand firmware/API upgrades, regression testing, releases, and long-term support. |
| [Q12. What would successful onboarding look like?](questions/12-onboarding-and-success.md) | Define the first assignment, available support, and 30/60/90-day outcomes. |

## Supporting material

| Document | Summary |
| --- | --- |
| [Architecture hypotheses](architecture-hypotheses.md) | Four discussion diagrams covering logical responsibilities, ground-side integration, onboard deployment, and mixed integration paths. |
| [Public evidence and reading](background-and-sources.md) | NODA's public statements, unresolved assumptions about MELD and URZA, official source links, and focused pre-reading. |
| [Interview discussion guide](discussion-guide.md) | Opening and closing prompts, five priority questions, candidate deliverables, hypothesis tracking, and a notes template. |
