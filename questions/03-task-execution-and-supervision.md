# Q3. Who owns task execution and supervision?

[Back to questions](../README.md)

**Source anchor:** [URZA overview](https://nodaintelligence.ai/) and [NODA's Intent Custody principle](https://nodaintelligence.ai/about/).

> For a simple sensor-data request, which component accepts the task, invokes the platform interface, observes progress, and decides that the result is complete? Where does an existing GCS participate?

Ask whether “supervision” is a separate service, adapter responsibility, or part of the existing OEM stack. What evidence can the operator inspect when the request was accepted but no result arrived?

| Distinction to clarify | Question |
| --- | --- |
| Transport delivery vs. application acceptance | Who knows that the recipient understood the request? |
| Acceptance vs. completion | Which result or observation demonstrates completion? |
| Connectivity loss vs. task failure | How are these represented separately? |
| Retry vs. a new request | Which layer owns duplicate handling and request identity? |
| Timeout vs. known outcome | Can the interface represent an unknown outcome? |

These are proposed interview distinctions, not a claimed MELD state machine. For protocol background, the [MAVLink command documentation](https://mavlink.io/en/services/command.html) explicitly distinguishes ordinary command acceptance from completion.

**Capture:** lifecycle owner, outcome evidence, and the engineer's responsibility at each boundary.

**Related context:** [Architecture hypotheses](../architecture-hypotheses.md) · [Discussion guide](../discussion-guide.md).
