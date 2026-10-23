# Interview Discussion Guide

[Back to overview](README.md)

Use the individual question documents for detailed prompts. This guide covers prioritization, concrete deliverables, hypothesis tracking, and interview notes.

Use these as follow-ups to the walkthrough, not a checklist to read aloud. Record the actual component, owner, and evidence behind each answer.

## Start with a concrete walkthrough

> I have been reading about MELD and URZA, and I drew a few possible integration boundaries. I would like to check my understanding rather than assume a particular implementation. Could we walk through a representative platform integration, using a non-sensitive example such as reading a sensor or requesting a health report? I am particularly interested in where the software runs, which interface it uses, and what the Taiwan integration engineer owns.

Let the engineer describe the system first. Then use the diagrams to resolve differences. Ask for interface shapes, ownership, and development practices; a representative example is enough.

### If only ten minutes are available

1. **Deployment:** Where does a typical partner adapter run, and what already exists at that location? See [Q2](questions/02-deployment-location.md).
2. **MELD contract:** What does an engineer implement to make a new platform MELD-compatible? See [Q1](questions/01-meld-integration-contract.md).
3. **Execution ownership:** Who turns a task into platform requests and decides whether it actually completed? See [Q3](questions/03-task-execution-and-supervision.md).
4. **Concrete deliverable:** Could you describe one recent integration, its hardest issue, and the artifacts required for acceptance? See [Q9](questions/09-integration-acceptance.md).
5. **Role boundary:** Which decisions and code changes would I own locally, and which need the core engineering or OEM team? See [Q10](questions/10-taiwan-role-and-ownership.md).

For a longer discussion, spend roughly five minutes on the walkthrough, ten on deployment and interfaces, ten on validation and ownership, and five reading back what you learned. Fit this into the interviewer's agenda.

## Translate the discussion into actual work

The following are **candidate deliverables to validate**, not a promise about NODA's internal process. Use them to turn broad answers into a concrete work breakdown.

| Work area | Possible artifact to ask about | Ownership question |
| --- | --- | --- |
| Interface discovery | Interface inventory, sample exchanges, capability gaps | Who supplies and approves the partner contract? |
| Adapter implementation | Reviewed code, package, configuration, API tests | Is this owned by Taiwan, core engineering, or the OEM? |
| Semantic integration | Capability profile, units/time mapping, documented limitations | Who approves the meaning of a successful result? |
| Runtime integration | Installation procedure, service health checks, resource measurements | Who owns the host environment and operational support? |
| Failure diagnosis | Minimal reproducer, trace bundle, causal explanation | Who coordinates a fix spanning multiple teams? |
| Validation | Repeatable fixtures, regression suite, acceptance report | Who decides that the integration is ready? |
| Partner handover | Interface Control Document, compatibility matrix, runbook | Who maintains these after the initial delivery? |
| Ongoing support | Upgrade assessment, reproducible field report, maintenance change | What is the expected support and travel commitment? |

One useful follow-up throughout the discussion:

> Could you show me the shape of that deliverable, or describe what was accepted for a previous integration?

## Record what changed in the architecture model

Do not convert a plausible answer into a universal rule. Record whether it describes one partner, the current default, or a product-wide requirement.

| Hypothesis | Current status | Evidence to request | Impact on the role |
| --- | --- | --- | --- |
| H1: A common capability/task contract separates orchestration from adapters | Unverified | Example interface and ownership boundary | Contract implementation and semantic testing |
| H2: An integration can remain entirely ground-side | Unverified | Representative supported external API deployment | OEM service integration and service operations |
| H3: An integration process can run on existing onboard compute | Unverified; check against public modification claim | Explicit supported deployment and qualification scope | Linux runtime and local-interface work |
| H4: Multiple deployment paths share a common upstream contract | Unverified | Two contrasting supported partner integrations | Reuse, compatibility, and broader test coverage |
| Zenoh is directly exposed to every adapter | Unverified | SDK/API boundary and supported transport model | Direct middleware work or SDK-level integration |
| A GCS owns task completion and supervision | Unverified | Lifecycle owner and outcome evidence | UI/service integration or another execution boundary |

### Notes template

```text
Question / hypothesis:
Representative platform or example:
Answer and scope (one integration / default / universal):
Actual component and deployment location:
Interface and version:
Taiwan engineer's deliverable:
Other owner or dependency:
Acceptance evidence:
Remaining uncertainty and follow-up:
```

### Close with a read-back

> Let me check that I understood. For this example, the adapter runs on [host] and connects to [existing interface]. It implements [contract], while [component] owns execution state and completion. My responsibility would be [deliverables], with acceptance based on [tests and evidence]. Is that accurate, and which parts vary between partners?

The desired outcome is a corrected architecture sketch, a concrete first assignment, and a clear division of responsibility—not agreement with the original diagram.
