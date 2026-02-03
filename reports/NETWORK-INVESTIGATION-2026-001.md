# NETWORK FORENSICS INVESTIGATION REPORT
**Case ID:** NETWORK-INVESTIGATION-2026-001  
**Date:** 2026-01-20  
**Analyst:** Renaldi 
**Threat:** VIP Recovery Malware with FTP Data Exfiltration  

## 🎯 EXECUTIVE SUMMARY

### Incident Overview
A system was infected with VIP Recovery information-stealing malware. The malware established command-and-control (C2) communication and exfiltrated sensitive data via FTP to an attacker-controlled server.

### Key Findings
- **Primary C2 Server:** `91.92.243.152` (19/93 security vendors flag as malicious)
- **Secondary C2 Server:** `193.122.6.168` (1/97 vendors flag as malicious)
- **Data Exfiltration:** FTP credentials stolen and files uploaded to remote server
- **Attack Duration:** Approximately 1 hour of monitored activity
- **Infrastructure:** Multi-layered C2 for redundancy and persistence

### Impact Assessment
**Severity:** HIGH  
**Data Compromised:** FTP credentials, unknown file contents  
**Persistence:** Established C2 channels for follow-on attacks

## 🔍 TECHNICAL ANALYSIS

### Attack Timeline
- 12:05:32 - Initial HTTP request to primary C2 (91.92.243.152)
- 12:10:15 - First beacon to secondary C2 (193.122.6.168)
- 12:22:48 - FTP authentication to attacker server
- 12:24:03 - File upload via FTP STOR command
- 12:30:45 - Continued beaconing to both C2 servers

### C2 Infrastructure Analysis

#### Primary C2: 91.92.243.152
- **Detection Rate:** 19/93 vendors (High confidence)
- **Protocol:** HTTP
- **Pattern:** Regular beaconing every ~5 minutes
- **Location:** Netherlands. Rotterdam, South Holland
- **Purpose:** Main command channel

#### Secondary C2: 193.122.6.168
- **Detection Rate:** 1/97 vendors (Low confidence)
- **Protocol:** HTTP
- **Pattern:** Irregular beaconing
- **Purpose:** Backup/fallback channel

### Data Exfiltration Details
**FTP Server:** 91.92.243.152
**Credentials Stolen:**
- Username: `user1369590`
- Password: `ojtEAL03p9s6`

**File Transferred:**
- Filename: ` ZyiAEnXWZP1116437875.txt`
- Size: 1.7 MB
- Protocol: FTP port 21

### Network Indicators
```yaml
# HTTP Traffic Patterns
- User-Agent: [Spesifik User-Agent jika ada]
- URI Paths: [/path1, /path2]
- Request Intervals: 300-360 seconds

# Behavioral Indicators
- Simultaneous connections to multiple C2 servers
- Plaintext credential transmission
- Regular interval beaconing
```
## 🎯 ATTACK CHAIN ANALYSIS
Infection → C2 Beaconing → Credential Harvest → File Upload → Persistence
(5-min intervals) (Plaintext FTP) (FTP STOR) (Scheduled tasks)

### Key TTPs:
- Multi-C2 redundancy for resilience
- Business-hour operations for blending
- Plaintext protocols to avoid encryption detection
- Low-volume exfiltration to reduce suspicion
