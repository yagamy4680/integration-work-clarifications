# Q7. What behavior is specified for interruptions and recovery?

[Back to questions](../README.md)

**Source anchor:** [NODA's communications-resilience description](https://nodaintelligence.ai/).

> For a representative sensor integration, what behavior is the adapter required to provide when the upstream service or partner connection disappears and later returns?

Keep the discussion at the software contract: what state is local, which observations become stale, whether data is buffered, how resource use is bounded, and how recovery is tested. Ask who specifies the behavior and which outcomes the platform can actually guarantee.

**Capture:** documented failure behavior, local responsibility, recovery criteria, and test ownership.

**Related context:** [Architecture hypotheses](../architecture-hypotheses.md) · [Discussion guide](../discussion-guide.md).
