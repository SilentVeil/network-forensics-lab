# 🔍 Network Forensics Lab - VIP Recovery Malware Analysis

## 🚨 Investigation Summary
Analysis of VIP Recovery malware with FTP data exfiltration (PCAP from 2026-01-20).

### Key Findings:
- C2 beaconing to malicious IP `193.122.6.168` (flagged by VirusTotal)
- FTP credentials theft and data exfiltration
- Clear attack chain: infection → credential theft → data theft → C2 persistence

### Screenshots:
![C2 Traffic](screenshots/wireshark-c2-traffic.png)
![Protocol Hierarchy](screenshots/protocol-hierarchy.png)
![FTP Credentials](screenshots/ftp-credentials.png)
![VirusTotal Detection](screenshots/virustotal-ip.png)

## 📊 Key Capabilities Demonstrated
- **Beaconing Detection** - C2 communication pattern analysis
- **Protocol Analysis** - HTTP/DNS/TLS anomaly identification  
- **File Extraction** - Malware carving from network streams
- **Timeline Reconstruction** - Attack chain visualization
- **Threat Hunting** - Proactive IOC detection & analysis
- **Automation** - Script development for repetitive tasks

  
## 📁 Repository Structure
```
network-forensics-lab/
├── README.md
├── pcaps/
│   └── VIP-Recovery-FTP-exfiltration.pcap  # PCAP yang sudah dianalisis
├── analysis/
│   ├── iocs.txt
│   ├── notes.txt
│   └── timeline.txt
├── scripts/
│   ├── beacon-detection.py
│   └── pcap-analysis.sh
├── screenshots/
│   ├── wireshark-c2-traffic.png
│   ├── protocol-hierarchy.png
│   ├── top-conversations.png
│   ├── virustotal-ip.png
│   └── ftp-credentials.png
├── reports/
│   └── NETWORK-INVESTIGATION-2026-001.md
└── docs/
    └── methodology.md
```




Renaldi | SOC & Cloud Security Analyst

