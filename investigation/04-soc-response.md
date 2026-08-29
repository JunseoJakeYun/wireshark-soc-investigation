# SOC Response

## Objective

Define the recommended response actions following the identification of a potentially compromised endpoint.

The response focuses on containment, investigation, eradication, recovery, and monitoring.

---

## 1. Containment

The immediate priority is to prevent the potentially compromised endpoint from causing further impact.

### Recommended Actions

- Isolate the affected endpoint from the network.
- Preserve the endpoint and relevant evidence before making significant changes.
- Prevent further communication with confirmed malicious infrastructure once validated.
- Escalate the incident according to the organisation's incident response process.

---

## 2. Account Protection

The associated user account should be reviewed for possible credential exposure.

### Recommended Actions

- Review recent authentication activity.
- Check for unusual or unexpected logins.
- Reset the user's password if credential compromise is suspected.
- Revoke active sessions or authentication tokens where applicable.
- Review any privileged access associated with the account.

---

## 3. Endpoint Investigation

The endpoint should be investigated to determine whether malicious software was executed and whether persistence was established.

### Areas to Investigate

- Recently downloaded files
- Running processes
- PowerShell and command-line activity
- Scheduled tasks
- Services
- Startup items
- Registry persistence
- Recently created or modified files
- EDR/antivirus alerts
- Windows Security Event Logs

The downloaded file should be preserved and analysed in a controlled environment.

---

## 4. IOC Hunting

Search the wider environment for the indicators identified during the investigation.

### Recommended Data Sources

- DNS logs
- Firewall logs
- Proxy logs
- EDR telemetry
- SIEM logs
- Web gateway logs
- Network monitoring data

The purpose is to determine whether the activity was isolated to one endpoint or affected additional systems.

---

## 5. Eradication

If endpoint investigation confirms malware or unauthorised activity:

- Remove confirmed malicious files.
- Remove persistence mechanisms.
- Remove unauthorised software.
- Run EDR/antivirus scans.
- Apply required security patches.
- Reset compromised credentials.
- Reimage the endpoint if its integrity cannot be trusted.

---

## 6. Recovery

The endpoint should only be returned to the production network after containment and eradication activities are complete.

### Recovery Checks

- Confirm malicious activity has stopped.
- Confirm the endpoint is no longer communicating with confirmed malicious infrastructure.
- Verify security controls are operational.
- Confirm required patches are installed.
- Restore normal network access.
- Continue monitoring after recovery.

---

## 7. Post-Incident Monitoring

Continue monitoring the affected endpoint and associated account for signs of recurring activity.

Monitor for:

- New suspicious DNS requests
- Unexpected outbound connections
- Unusual authentication activity
- Suspicious processes or services
- Reappearance of malicious files
- Similar activity on other endpoints


# Analyst Assessment

Based on the network investigation, the endpoint should be treated as potentially compromised.

The appropriate response would be to contain the endpoint first, preserve relevant evidence, and then determine the scope and impact of the incident.

Endpoint and account investigation should be completed before returning the system to normal operation.

If compromise is confirmed, malicious activity and persistence should be removed, followed by recovery and continued monitoring.
