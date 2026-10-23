# Q6. How are platform identity and current state represented?

[Back to questions](../README.md)

**Source anchor:** [NODA interoperability principles](https://nodaintelligence.ai/about/). This is a proposed integration-contract question; the public page does not specify an identity mechanism.

> How does a stable platform identity map to its current process, middleware session, and OEM protocol address? What changes after a restart or hardware replacement?

Ask whether the integration engineer manages registration and mappings or consumes an existing service. How are duplicate identities, stale telemetry, and incompatible schema versions surfaced? Which component authorizes an adapter to represent a platform?

**Capture:** identity source, mapping owner, freshness rules, and the available validation checks.

**Related context:** [Architecture hypotheses](../architecture-hypotheses.md) · [Discussion guide](../discussion-guide.md).
