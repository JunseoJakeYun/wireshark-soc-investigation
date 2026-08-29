# Attack Timeline

## Objective

Reconstruct the sequence of suspicious activity observed in the PCAP and show how the investigation progressed from the initial event to the identified C2 communications.

---

## Timeline

| Time (UTC) | Event | Significance |
|---|---|---|
| `19:44:56` | Internal network activity observed | Establishes the beginning of the observed activity |
| `19:45:35` | Connection to suspicious web infrastructure observed | Potential initial suspicious web activity |
| `19:45:35` | TLS session established | Encrypted communication begins |
| `19:45:35 – 19:46:49` | Continued encrypted communication | Sustained communication with the suspicious infrastructure |
| `19:47:05` | HTTP communication with `5.252.153.241` begins | First clearly observed C2-like communication |
| `19:47:05 onward` | HTTP requests repeated at approximately 5-second intervals | Consistent with automated beaconing |
| `19:59+` | Additional suspicious external communications observed | Further C2 infrastructure identified |

---

## Communication Sequence

```text
Initial suspicious web activity
            |
            v
     Encrypted traffic
            |
            v
  External connections reviewed
            |
            v
  Repeated HTTP communication
            |
            v
   Automated beaconing observed
            |
            v
 Additional suspicious C2
   communications identified
```

---

## Key Timeline Finding

The most significant change in network behaviour was the transition from the initial suspicious web activity to repeated automated communication with an external destination.

The repeated requests to `5.252.153.241` occurred at approximately five-second intervals, which was a key behavioural indicator used to identify potential C2 activity.

Additional suspicious external communications were subsequently identified during the same investigation.

---

## Analyst Assessment

The timeline indicates that the suspicious activity was not limited to a single web connection.

Following the initial suspicious web activity, the affected endpoint continued communicating with external infrastructure and later demonstrated repeated, automated communication patterns.

The timeline supports the conclusion that the incident involved ongoing network communication rather than a single isolated connection.

Detailed analysis of the individual destinations and the evidence supporting their classification as C2 is documented separately in:

- `01-initial-investigation.md`
- `02-c2-investigation.md`
