# NODA AI: Integration Discussion

A few topics I'd like to explore with the engineering team to better understand NODA's architecture and the Systems Software Integration Engineer role in Taiwan.

## Discussion topics

| Topic | Summary |
| --- | --- |
| [1. Working with MELD](questions/01-meld-integration-contract.md) | The interface and code involved in adding a new platform. |
| [2. Where the integration runs](questions/02-deployment-location.md) | Deployment locations and existing partner interfaces. |
| [3. From task to completion](questions/03-task-execution-and-supervision.md) | How URZA, adapters, and existing systems share execution and monitoring. |
| [4. Different platform capabilities](questions/04-capability-mapping.md) | Representing capabilities and handling unsupported requests. |
| [5. Zenoh and networking](questions/05-zenoh-and-multicast.md) | Middleware, multicast, and the networking work involved in integration. |
| [6. Platform identity and state](questions/06-platform-identity-and-state.md) | Recognizing platforms across connections and restarts. |
| [7. Connection loss and recovery](questions/07-interruptions-and-recovery.md) | What an adapter handles when a connection drops and returns. |
| [8. Debugging across systems](questions/08-cross-system-debugging.md) | The team's approach to diagnosing issues across technical boundaries. |
| [9. Testing an integration](questions/09-integration-acceptance.md) | The path from a working connection to deployment readiness. |
| [10. Working with the team](questions/10-taiwan-role-and-ownership.md) | Responsibilities shared by the Taiwan engineer, core team, and OEMs. |
| [11. Maintaining an integration](questions/11-compatibility-and-maintenance.md) | Firmware/API updates and support after the first release. |
| [12. Getting started](questions/12-onboarding-and-success.md) | A first project, learning resources, and early expectations. |

## Background

| Document | Summary |
| --- | --- |
| [Integration sketches](architecture-hypotheses.md) | Four possible views of the system to help discuss interfaces and deployment locations. |
| [Background and references](background-and-sources.md) | My starting understanding of MELD and URZA, with links to the public material. |
| [Example integration walkthrough](discussion-guide.md) | A simple sensor example to connect the architecture with everyday integration work. |
