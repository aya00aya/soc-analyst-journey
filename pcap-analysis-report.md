# PCAP Analysis Report

## Exercise Information
- **Exercise Date:** 2026-02-28
- **Exercise Name:** Easy as 123
- **Environment:** 10.2.28.0/24 LAN
- **Domain:** easyas123.tech

## Key Findings

### Victim Information
- **Internal IP:** 10.2.28.88
- **MAC Address:** [from Ethernet section]
- **Hostname:** [from NBNS/DNS]
- **Role:** Infected host

### Attacker Information
- **External IP:** 45.131.214.85
- **Port:** 443 (HTTPS/TLS)
- **Role:** Command-and-control (C2) server
- **Packets Exchanged:** 550

### Protocols Observed
- **TCP:** Connection-oriented communication
- **TLS/HTTPS:** Encrypted traffic over port 443
- **DNS:** Name resolution (if applicable)

## Suspicious Patterns Identified
1. The victim machine (`10.2.28.88`) communicated exclusively with known malicious IP `45.131.214.85`
2. Communication occurred over encrypted HTTPS (port 443), making content analysis difficult
3. [Add any beaconing or data exfiltration patterns you found]

## Summary
On 2026-02-28 at approximately 19:55 UTC, the internal host at `10.2.28.88` was observed communicating with the malicious IP `45.131.214.85` over TCP port 443. This matches the SIEM alert that triggered the investigation. The encrypted communication suggests the host may have been compromised and is communicating with a command-and-control server.

## Indicators of Compromise (IOCs)
- **IP Address:** 45.131.214.85
- **Port:** 443

## Victim Information
- **Internal IP:** 10.2.28.88
- **MAC Address:** 00:19:d1:b2:4d:ad (Intel)
- **Hostname:** [We still need to find this!]
- **Protocol:** TCP/TLS
- **Victim IP:** 10.2.28.88
