# PCAP Analysis Report

## Exercise Information
- **Exercise Date:** 2026-02-28
- **Exercise Name:** Easy as 123
- **Environment:** 10.2.28.0/24 LAN
- **Domain:** easyas123.tech

## Key Findings

### Victim Information
| Info | Details |
|------|---------|
| **Internal IP** | 10.2.28.88 |
| **MAC Address** | 00:19:d1:b2:4d:ad |
| **MAC Vendor** | Intel |
| **Hostname** | DESKTOP-5AVE44C |
| **Role** | Infected host (communicating with C2 server) |

### Attacker Information
| Info | Details |
|------|---------|
| **External IP** | 45.131.214.85 |
| **Port** | 443 |
| **Protocol** | HTTPS/TLS |
| **Role** | Command-and-control (C2) server |
| **Packets Exchanged** | 550 |

### Protocols Observed
| Protocol | Purpose |
|----------|---------|
| **TCP** | Establishes and maintains the connection |
| **TLS/HTTPS** | Encrypted communication over port 443 |
| **DNS** | Name resolution (initial lookups) |

## Suspicious Patterns Identified

1. **Exclusive Communication:** The victim machine (`10.2.28.88`) communicated exclusively with the malicious IP (`45.131.214.85`)

2. **Encrypted Traffic:** All communication occurred over encrypted HTTPS (port 443), making content analysis difficult—a common tactic used by malware to hide its activities

3. **SIEM Alert Matched:** The IP `45.131.214.85` was already flagged by the SIEM as suspicious, confirming the alert was valid

## Summary

On **2026-02-28 at approximately 19:55 UTC**, the internal host at **10.2.28.88** (hostname: `DESKTOP-5AVE44C`, MAC: `00:19:d1:b2:4d:ad`) was observed communicating with the malicious IP **45.131.214.85** over TCP port 443.

**What happened:**
- The victim and attacker exchanged **550 packets**
- The communication was encrypted using **HTTPS/TLS** to hide the content
- This matches the **SIEM alert** that triggered the investigation

**Conclusion:**
The encrypted communication pattern strongly suggests the host may have been compromised and was communicating with a command-and-control (C2) server, likely receiving instructions or exfiltrating data.

## Indicators of Compromise (IOCs)

| IOC | Value |
|-----|-------|
| **Attacker IP** | 45.131.214.85 |
| **Attacker Port** | 443 |
| **Protocol** | TCP/TLS |
| **Victim IP** | 10.2.28.88 |
| **Victim MAC** | 00:19:d1:b2:4d:ad |
| **Victim Hostname** | DESKTOP-5AVE44C |

## Recommendations

1. **Isolate** the infected host (`10.2.28.88`) from the network immediately
2. **Run a full antivirus scan** on the infected machine
3. **Block** the malicious IP (`45.131.214.85`) at the firewall
4. **Monitor** for any other hosts communicating with this IP

---

**Report by:** [Your Name]  
**Date:** [Today's Date]  
**Exercise Source:** Malware Traffic Analysis - Easy as 123

![Wireshark Evidence](image.png)
