# Integration Sketches

I drew these sketches to help explain my current understanding. The interfaces and deployment locations are assumptions for discussion; I'd appreciate your corrections or a different view that better reflects the system.

## 1. MELD, URZA, and partner interfaces

Does this roughly reflect how URZA, MELD, and partner integrations fit together? Where would you place responsibility for tracking task completion?

```mermaid
flowchart TB
    C2["Operator application or existing C2"]
    U["URZA: reasoning and tasking"]
    M["MELD interface: to discuss"]
    A["Partner-specific integration"]
    G["Existing OEM GCS or service API"]
    P["Existing platform or sensor API"]
    C2 -->|"Intent and constraints"| U
    U -->|"Task request"| M
    M --> A
    A --> G
    A --> P
    G -->|"State and results"| A
    P -->|"State and results"| A
    A -->|"Normalized feedback"| M
    M -->|"Capabilities and task state"| U
    U -->|"Progress and exceptions"| C2
```

Reference: [NODA overview](https://nodaintelligence.ai/). Related: [Working with MELD](questions/01-meld-integration-contract.md) and [From task to completion](questions/03-task-execution-and-supervision.md).

## 2. Integration through a ground-side interface

Could an integration use an existing OEM ground control station or gateway API, as shown here?

```mermaid
flowchart TB
    U["NODA orchestration runtime: location TBD"]
    subgraph GROUND["Possible ground-side integration"]
        A["NODA adapter A"]
        B["NODA adapter B"]
        GA["Existing OEM A GCS or gateway"]
        GB["Existing OEM B GCS or gateway"]
        A <-->|"Existing OEM API"| GA
        B <-->|"Existing OEM API"| GB
    end
    VA["Platform group A: existing radio network"]
    VB["Platform B: existing radio link"]
    U <-->|"Integration interface TBD"| A
    U <-->|"Integration interface TBD"| B
    GA <-->|"Existing vendor link"| VA
    GB <-->|"Existing vendor link"| VB
```

Reference: [NODA integration announcement](https://nodaintelligence.ai/news/department-of-war-awards-noda-ai-100-million-to-scale-mission-command-for-autonomous-forces-across-the-joint-force/).

## 3. Integration on an existing onboard computer

Is an integration process on an existing companion computer ever part of the setup? If so, how does it fit with the approach of leaving the OEM platform unchanged?

```mermaid
flowchart TB
    U["NODA orchestration runtime: location TBD"]
    G["Existing OEM GCS"]
    subgraph VEHICLE["Possible placement on existing vehicle hardware"]
        E["Integration runtime on existing companion computer"]
        O["Existing OEM autonomy API"]
        F["Existing vehicle controller"]
        S["Existing sensor interface"]
        E <-->|"Supported local interface"| O
        O <--> F
        O <--> S
    end
    U <-->|"Existing network transport"| E
    G <-->|"Existing OEM management path"| O
```

Reference: [NODA platform principles](https://nodaintelligence.ai/solutions/) and [integration announcement](https://nodaintelligence.ai/news/department-of-war-awards-noda-ai-100-million-to-scale-mission-command-for-autonomous-forces-across-the-joint-force/).

## 4. Different integration paths

Can different partners use different integration paths while exposing a common interface to NODA? Which parts of the integration are usually reusable?

```mermaid
flowchart TB
    U["URZA runtime or runtimes: TBD"]
    M["Shared integration interface: to discuss"]
    GA["Ground-side adapter"]
    EA["Optional existing-compute adapter"]
    OA["OEM-provided compatible endpoint"]
    G["OEM GCS API"]
    P["Platform-local API"]
    O["OEM service or autonomy API"]
    U <-->|"Tasks and feedback"| M
    M <--> GA
    M <--> EA
    M <--> OA
    GA <--> G
    EA <--> P
    OA <--> O
```

Reference: [NODA platform principles](https://nodaintelligence.ai/solutions/).

[Deployment discussion](questions/02-deployment-location.md) · [All topics](README.md)
