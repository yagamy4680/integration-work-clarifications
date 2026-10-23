# Public Evidence and Reading

[Back to overview](README.md)

An English discussion guide for the **Systems Software Integration Engineer — Taiwan** interview.

**Goal:** understand the product boundaries, locate the integration work, and learn what this engineer would own from a partner's first connection through a supported release.

**Public sources reviewed:** October 23, 2026. All diagrams are candidate hypotheses for discussion, not NODA architecture documentation. Component names such as “adapter” and “execution supervisor” are descriptive placeholders unless the interviewer confirms them.

## Establish the evidence before drawing conclusions

| Topic | What the public material supports | What still needs confirmation |
| --- | --- | --- |
| MELD | NODA calls MELD its open integration standard. [S1](https://nodaintelligence.ai/) | Is the integration surface a specification, SDK, service API, runtime, or a combination? What does “open” mean for implementers? |
| URZA | NODA describes a reasoning engine and task broker that translates intent and adapts tasking. [S1](https://nodaintelligence.ai/) | Runtime placement, adapter boundaries, and division of responsibility with existing platform autonomy. |
| Existing platforms | NODA's announcement says its integration platform requires no hardware or software changes to OEM or government platforms. Its technology page also emphasizes hardware independence. [S4](https://nodaintelligence.ai/news/department-of-war-awards-noda-ai-100-million-to-scale-mission-command-for-autonomous-forces-across-the-joint-force/), [S2](https://nodaintelligence.ai/solutions/) | Preconditions, supported interfaces, and where NODA-owned integration code executes. |
| Distributed operation | NODA describes continuity under impaired communications. [S1](https://nodaintelligence.ai/) | Which functions remain available locally and what guarantees apply to a particular integration. |
| Taiwan role | The posting covers adapter development, cross-layer diagnosis, validation, partner coordination, interface documentation, and observability. [S5](https://jobs.ashbyhq.com/noda-ai/8253e820-f565-4428-8aaf-b6284ca2d450) | The first assignment, ownership boundaries, available support, and acceptance criteria. |

### Working interpretation of MELD and URZA

Treat **MELD as the integration boundary** and **URZA as the reasoning/tasking responsibility** until the engineer provides a more precise model. This is a useful starting abstraction, not a verified software stack.

The description of MELD as a universal middleware layer is a working interpretation. The reviewed public pages do not provide enough detail to identify a public MELD schema, SDK, conformance suite, or source-code license. Ask for the appropriate documentation rather than treating “open standard” as proof of open-source implementation.

Likewise, “task broker” describes URZA's application role. It does not establish that URZA is a transport broker or a Zenoh router. The job posting mentions Zenoh or comparable middleware, but it does not establish that MELD equals Zenoh or that every connection uses it.

The key question behind “no platform modifications” is: **what existing capability and accessible interface must a partner already provide?** Integration code can adapt an available capability; a new message format alone cannot create a missing platform capability.

## Sources and focused pre-reading

Company statements below are evidence of NODA's public positioning, not independent verification of implementation. The diagrams, questions, and proposed work artifacts are original discussion aids.

| ID | Primary source | Read for |
| --- | --- | --- |
| S1 | [NODA AI overview](https://nodaintelligence.ai/) | URZA, MELD terminology, capability abstraction, and stated resilience |
| S2 | [NODA technology and platform principles](https://nodaintelligence.ai/solutions/) | Hardware independence, interoperability, and simulation positioning |
| S3 | [NODA values](https://nodaintelligence.ai/about/) | Intent Custody and the expectations behind trust |
| S4 | [NODA integration announcement — August 17, 2026](https://nodaintelligence.ai/news/department-of-war-awards-noda-ai-100-million-to-scale-mission-command-for-autonomous-forces-across-the-joint-force/) | Exact scope of the public hardware/software modification claim |
| S5 | [Official Taiwan job posting](https://jobs.ashbyhq.com/noda-ai/8253e820-f565-4428-8aaf-b6284ca2d450) | Stated responsibilities and required technical depth; also reachable through [NODA Careers](https://nodaintelligence.ai/careers/) |
| S6 | [Zenoh deployment documentation](https://zenoh.io/docs/getting-started/deployment/) | Middleware topology and discovery; not NODA's deployment specification |
| S7 | [MAVLink command protocol](https://mavlink.io/en/services/command.html) | Delivery, acceptance, progress, and completion distinctions; not MELD's task contract |

**Suggested 35-minute preparation:** ten minutes on S1/S2/S4, five on S5, ten comparing the three deployment hypotheses, and ten rehearsing the opening, five priority questions, and closing read-back. Use S6/S7 for a focused refresher if those boundaries become relevant.

See the [discussion guide](discussion-guide.md) for the opening, priority questions, and closing read-back.
