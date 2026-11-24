# Enterprise Detection Engineering Lab

## 1. Project Overview

This project demonstrates the design, implementation, and validation of an enterprise-style Security Information and Event Management (SIEM) environment using Microsoft Sentinel, Azure Monitor, Windows Server, Sysmon, and Kusto Query Language (KQL).

The project simulates real-world Security Operations Center (SOC) and detection engineering workflows, including security telemetry collection, log analysis, threat detection, incident investigation, and detection optimization.

## 2. Project Objectives

- Design an enterprise-style SIEM architecture.
- Collect Windows Security and Sysmon event logs.
- Configure centralized security telemetry ingestion.
- Develop KQL queries for security investigations.
- Build and validate threat detection rules.
- Map detections to the MITRE ATT&CK framework.
- Investigate and document security incidents.
- Identify false positives and improve detection accuracy.
- Maintain version-controlled detection logic and technical documentation.

## 3. Technologies and Tools

| Technology | Purpose |
|---|---|
| Microsoft Azure | Cloud infrastructure |
| Microsoft Sentinel | SIEM and SOAR |
| Windows Server | Endpoint and security event generation |
| Sysmon | Detailed endpoint telemetry |
| Azure Monitor Agent (AMA) | Event collection |
| Data Collection Rules (DCR) | Log collection configuration |
| Log Analytics Workspace | Centralized log storage and analysis |
| Kusto Query Language (KQL) | Threat hunting and detection logic |
| PowerShell | Administration and controlled testing |
| MITRE ATT&CK | Threat behavior classification |
| GitHub | Version control and project documentation |

## 4. SIEM Architecture

The proposed architecture follows a centralized security monitoring model.

**Data flow:**

Windows Server → Windows Security Logs and Sysmon → Azure Monitor Agent → Log Analytics Workspace → Microsoft Sentinel → Analytics Rules → Security Incidents

Data Collection Rules determine which event channels are collected and where the telemetry is delivered.

[View the detailed SIEM architecture](architecture/siem-architecture.md)

## 5. Security Log Sources

| Log Source | Event ID | Description |
|---|---|---|
| Windows Security | 4624 | Successful logon |
| Windows Security | 4625 | Failed logon |
| Windows Security | 4672 | Special privileges assigned at logon |
| Windows Security | 4688 | Process creation |
| Windows Security | 4720 | User account creation |
| Windows Security | 4732 | Member added to a security-enabled local group |
| Sysmon | 1 | Process creation |
| Sysmon | 3 | Network connection |
| Sysmon | 11 | File creation |
| Sysmon | 22 | DNS query |

Event availability depends on the Windows audit policy, Sysmon configuration, and data collection settings.

## 6. Planned Detection Use Cases

| Detection | MITRE ATT&CK | Status |
|---|---|---|
| Repeated failed logons | T1110 – Brute Force | Pending |
| Password spraying | T1110.003 – Password Spraying | Pending |
| Suspicious PowerShell execution | T1059.001 – PowerShell | Pending |
| Suspicious account creation | T1136 – Create Account | Pending |
| Suspicious group membership changes | T1098 – Account Manipulation | Pending |

Each detection will include a hypothesis, data source, KQL logic, severity, test results, false-positive considerations, and investigation recommendations.

## 7. KQL Query Development

The project will include queries for:

- Windows Security event analysis
- Successful and failed authentication
- Event frequency analysis
- Sysmon process execution
- Authentication trends
- Suspicious PowerShell activity
- Privileged account activity

Queries will be maintained in the `queries/` directory.

## 8. Test and Validation Plan

| Test ID | Test Description | Expected Result | Status |
|---|---|---|---|
| TC-001 | Verify Windows VM availability | VM accessible | Pending |
| TC-002 | Verify Sysmon installation | Sysmon service running | Pending |
| TC-003 | Launch a benign test process | Sysmon Event ID 1 generated | Pending |
| TC-004 | Verify AMA deployment | Agent provisioning successful | Pending |
| TC-005 | Verify DCR association | Windows VM associated | Pending |
| TC-006 | Validate Sysmon ingestion | Sysmon events available in Log Analytics | Pending |
| TC-007 | Validate Windows Security ingestion | Security events available in Log Analytics | Pending |
| TC-008 | Generate a controlled failed logon | Event ID 4625 recorded | Pending |
| TC-009 | Execute KQL investigation queries | Expected event records returned | Pending |
| TC-010 | Validate detection logic | Positive and negative tests behave as expected | Pending |
| TC-011 | Validate Sentinel analytics rule | Expected alert and incident generated | Pending |
| TC-012 | Perform incident investigation | Investigation documented | Pending |

Tests will be marked as passed only after successful execution and evidence collection.

## 9. Project Roadmap

### Phase 1 — SIEM Architecture and Telemetry

- [ ] Design SIEM architecture
- [ ] Configure Windows Server
- [ ] Install and validate Sysmon
- [ ] Configure Azure Monitor Agent
- [ ] Configure Data Collection Rules
- [ ] Validate log ingestion
- [ ] Develop foundational KQL queries

### Phase 2 — Detection Engineering

- [ ] Develop brute-force detection
- [ ] Develop password-spray detection
- [ ] Develop suspicious PowerShell detection
- [ ] Develop account manipulation detection
- [ ] Map detections to MITRE ATT&CK
- [ ] Perform positive and negative testing

### Phase 3 — Incident Investigation

- [ ] Configure Sentinel analytics rules
- [ ] Generate controlled security incidents
- [ ] Investigate alerts and entities
- [ ] Build incident timelines
- [ ] Document findings and recommendations

### Phase 4 — Detection Optimization and Automation

- [ ] Analyze false positives
- [ ] Tune detection thresholds
- [ ] Implement detection-as-code practices
- [ ] Explore automated incident enrichment
- [ ] Document detection performance

## 10. Repository Structure

```text
enterprise-detection-engineering/
├── README.md
├── architecture/
│   └── siem-architecture.md
├── docs/
│   ├── windows-event-ids.md
│   ├── sysmon-validation.md
│   └── telemetry-checkpoint.md
├── queries/
├── detections/
├── test-results/
├── incident-reports/
└── screenshots/
```

This is the planned repository structure. Directories and files will be added as implementation progresses.

## 11. Performance and Validation Metrics

The following metrics will be recorded during testing:

| Metric | Measured Result |
|---|---|
| Validated log sources | Not yet measured |
| Total ingested events | Not yet measured |
| Working KQL queries | Not yet measured |
| Validated detection rules | Not yet measured |
| Detection test pass rate | Not yet measured |
| Observed ingestion latency | Not yet measured |
| Mean Time to Detect (MTTD) | Not yet measured |
| Mean Time to Respond (MTTR) | Not yet measured |

All reported metrics will be based on observed lab results.

## 12. Project Status

**Current status: In Progress**

**Current phase:** Week 1 — SIEM Architecture, Log Sources, and KQL Fundamentals.

The initial focus is establishing a reliable security telemetry pipeline and validating event ingestion before implementing advanced detection rules.

## 13. Skills Demonstrated Through This Project

The project is designed to develop and demonstrate competencies in:

- Security engineering
- Detection engineering
- SIEM architecture
- Cloud security monitoring
- Windows security event analysis
- KQL development
- Threat hunting
- Incident investigation
- Detection validation and tuning
- Technical documentation
- Git-based version control

## 14. Security and Ethical Considerations

All testing is performed within an authorized, isolated lab environment for defensive cybersecurity education.

No production systems or unauthorized third-party resources are targeted. Sensitive identifiers, credentials, and personal information are removed from publicly shared evidence.

## 15. References

- [Microsoft Sentinel Documentation](https://learn.microsoft.com/en-us/azure/sentinel/)
- [Azure Monitor Agent Documentation](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-overview)
- [Sysmon Documentation](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
- [Kusto Query Language Documentation](https://learn.microsoft.com/en-us/kusto/query/)
- [MITRE ATT&CK Framework](https://attack.mitre.org/)

---

*An enterprise-style cybersecurity portfolio project focused on detection engineering, security monitoring, and cloud security.*
