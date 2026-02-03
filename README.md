# 🔍 Network Forensics Lab - Malware Traffic Analysis

## 🎯 Overview
A hands-on network forensic investigation lab analyzing malicious PCAP files to detect command-and-control (C2) beaconing, data exfiltration, and malware communication patterns. This project demonstrates real SOC threat hunting skills using industry-standard tools.

## 🚨 Investigation Scenario
**Malware:** Emotet Trojan variant  
**Attack Chain:** Malware download → C2 beaconing → Data exfiltration  
**Source:** Real malware traffic from Malware-Traffic-Analysis.net (sanitized)

## 🛠️ Analysis Methodology
1. **Initial Triage** - Protocol distribution, conversation mapping
2. **Anomaly Detection** - Beaconing patterns, unusual ports
3. **C2 Identification** - Regular intervals, encrypted channels  
4. **Data Exfiltration** - Large transfers, unusual destinations
5. **IOC Extraction** - IPs, domains, SSL certificates, file hashes

## 📁 Repository Structure
```
network-forensics-lab/
├── README.md
├── pcaps/
│   ├── malware-traffic.pcap
│   └── clean-baseline.pcap
├── analysis/
│   ├── iocs.txt
│   ├── timeline.txt
│   ├── suricata-alerts.log
│   └── extracted-files/
├── scripts/
│   ├── beacon-detection.py
│   ├── pcap-analysis.sh
│   └── ioc-extractor.py
├── screenshots/
│   ├── wireshark-overview.png
│   ├── c2-beaconing.png
│   └── tshark-output.png
├── reports/
│   └── NETWORK-INVESTIGATION-2024-001.md
└── docs/
    ├── methodology.md
    └── tools-guide.md
```

## 🚀 Quick Start
```bash
# Clone repository
git clone https://github.com/SilentVeil/network-forensics-lab.git
cd network-forensics-lab

# Analyze PCAP with tshark
tshark -r pcaps/malware-traffic.pcap -Y "http"

# Run beacon detection script
python scripts/beacon-detection.py pcaps/malware-traffic.pcap
```

## 🔧 Tools Used
- **Primary Analysis:** Wireshark (GUI), tshark (CLI)
- **File Extraction:** NetworkMiner
- **IOC Processing:** Python scripts with Scapy
- **Logging & Reporting:** Markdown, MITRE ATT&CK Navigator
- **Environment:** Ubuntu VM with security tools suite

## 📊 Key Capabilities
- **Beaconing Detection** - C2 communication pattern analysis
- **Protocol Analysis** - HTTP/DNS/TLS anomaly identification  
- **File Extraction** - Malware carving from network streams
- **Timeline Reconstruction** - Attack chain visualization
- **Threat Hunting** - Proactive IOC detection & analysis
- **Automation** - Script development for repetitive tasks


👨‍💻 Author
Renaldi | SOC & Cloud Security Analyst

