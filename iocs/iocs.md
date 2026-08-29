# Indicators of Compromise (IOCs)

## Affected Endpoint

| Type | Value | Description |
|---|---|---|
| IP Address | `10.1.17.215` | Suspected compromised Windows client |
| Hostname | `DESKTOP-L8C5GSJ` | Hostname identified through NBNS |
| Username | `shutchenson` | User identified through Kerberos traffic |

## Initial Access Infrastructure

| Type | Value | Description |
|---|---|---|
| Domain | `authenticatoor.org` | Suspicious website associated with the reported download |
| IP Address | `82.221.136.26` | IP associated with the suspicious website |

## Command and Control (C2)

| Type | Value | Evidence |
|---|---|---|
| IP Address | `5.252.153.241` | Repeated HTTP beaconing approximately every 5 seconds |
| IP Address | `45.125.66.32` | TLS communication over TCP/2917 with self-signed certificate |
| IP Address | `45.125.66.252` | TLS communication over TCP/443 with self-signed certificate |

## Investigation Notes

The IOC list was developed from packet-level analysis of the provided PCAP using Wireshark.

The C2 IP addresses were identified based on communication patterns and supporting network indicators rather than simply matching known IOC lists.
