
# Enterprise SIEM Architecture

```mermaid
flowchart TD
    A[Windows Server VM]
    B[Windows Security and System Logs]
    C[Sysmon Operational Log]
    D[Azure Monitor Agent]
    E[Data Collection Rule]
    F[Log Analytics Workspace]
    G[Microsoft Sentinel]
    H[KQL Analytics Rules]
    I[Alerts and Incidents]
    J[SOC Investigation]

    A --> B
    A --> C
    B --> D
    C --> D
    E -. Configures .-> D
    D --> F
    F --> G
    G --> H
    H --> I
    I --> J
```

## Architecture Explanation

Windows generates operating system and security events.
Sysmon adds detailed endpoint telemetry.
Azure Monitor Agent collects selected events according
to the Data Collection Rule and sends them to Log Analytics.

Microsoft Sentinel uses the workspace data for KQL
hunting queries, scheduled analytics rules, and incidents.
