# SIEM Telemetry Ingestion Validation

## Objective

Validate Windows Security and Sysmon event ingestion into Azure Log Analytics for Microsoft Sentinel security monitoring.

## Lab Environment

- Windows VM: SOC-DC01
- Log Analytics Workspace: LAW-SOC
- Collection Agent: Azure Monitor Agent
- Collection Configuration: Data Collection Rules
- SIEM: Microsoft Sentinel

## Validation Results

| Test ID | Test Description | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| ING-001 | Agent heartbeat | Recent heartbeat received | Pending | Not tested |
| ING-002 | Sysmon ingestion | Sysmon events received | Pending | Not tested |
| ING-003 | Windows Security ingestion | Security events received | Pending | Not tested |
| ING-004 | Live process creation | Notepad process event received | Pending | Not tested |
| ING-005 | Ingestion latency | Latency metrics calculated | Pending | Not tested |

## Performance Metrics

| Metric | Observed Result |
|---|---|
| Total Sysmon events | Pending |
| Total Windows Security events | Pending |
| Average ingestion latency | Pending |
| P95 ingestion latency | Pending |
| Validated log sources | Pending |

## Evidence

Sanitized screenshots will be stored in the `screenshots/ingestion-validation/` directory.

## Conclusion

The telemetry pipeline will be considered operational after agent connectivity, Windows Security event ingestion, Sysmon event ingestion and live event collection have been successfully validated.

**Project Status:** In Progress.
