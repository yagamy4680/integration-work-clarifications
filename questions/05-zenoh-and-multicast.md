# Q5. Where does Zenoh fit, and what does multicast refer to?

[Back to questions](../README.md)

**Source anchor:** [Taiwan job posting](https://jobs.ashbyhq.com/noda-ai/8253e820-f565-4428-8aaf-b6284ca2d450). Technical background: [Zenoh deployment documentation](https://zenoh.io/docs/getting-started/deployment/).

> Does a partner adapter use Zenoh directly, or does a NODA SDK hide transport details? When the role mentions multicast, is the relevant work discovery, application data, or integration with another network component?

Zenoh documents peer, client, and router deployment modes and multicast-based discovery. That does not establish NODA's configuration or imply that application data is multicast over every radio link.

Ask which configuration is supported, how restricted discovery environments are handled, and who owns middleware version compatibility. Does the assignment include commissioning radios, or integrating software over a partner-provided network? For capacity or co-site interference problems, clarify the diagnostics expected from this role and when a network or RF specialist joins the investigation.

**Capture:** middleware boundary, supported configuration, diagnostic access, and specialist ownership.

**Related context:** [Architecture hypotheses](../architecture-hypotheses.md) · [Discussion guide](../discussion-guide.md).
