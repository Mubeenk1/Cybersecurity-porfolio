# Zeek Network Analysis Projects

## 🛡️ About Zeek

Zeek is an open-source, commercial-grade network analysis tool designed for in-depth traffic inspection and threat detection. It provides powerful network visibility through detailed, human-readable logs and is capable of detecting complex threats across a wide range of protocols.

## 📁 About This Folder

This folder contains practical Zeek projects in pdf format which I completed on hands-on cybersecurity platforms like **TryHackMe**, **Hack The Box**, and others. These labs helped me:

- Understand and analyze real-world network traffic using Zeek
- Write and test custom Zeek scripts for threat detection
- Practice using Zeek filters and log analysis techniques
- Investigate protocols such as DNS, HTTP, SSH using protocol-based logs
- Detect anomalies and suspicious behaviors using `conn.log`, `notice.log`, and `intel.log`

Through these exercises, I developed strong foundational skills in **Network Analysis using Zeek**


Zeek operates in two main layers:

### 1. Event Engine
This is responsible for processing captured network packets. It identifies events like connections, sessions, and file transfers without interpreting their semantic context. Key tasks include:
- Parsing source/destination IPs
- Protocol identification (TCP, UDP, etc.)
- Session analysis
- File extraction

### 2. Policy Script Interpreter
This layer semantically analyzes and correlates events using Zeek’s scripting language. It allows users to:
- Automate detection
- Write custom logic
- Investigate specific behaviors or patterns

## 🚀 Zeek Operating Modes
Zeek can run in two modes:
1. **Live mode as a service** using `zeekctl`
2. **Offline mode** by processing `.pcap` files (e.g., `zeek -C -r file.pcap`)

## 📁 Zeek Log Categories
Zeek produces logs across 7 main categories:
- **Network** (e.g., `conn.log`, `ssl.log`)
- **Files** (e.g., `files.log`)
- **Detection** (e.g., `intel.log`, `notice.log`)
- **Net Control**
- **Observation** (e.g., `software.log`, `known_hosts.log`)
- **Miscellaneous**
- **Diagnostics**

### ✳️ Common Logs:
| Category       | Example Logs                      |
|----------------|-----------------------------------|
| **Connection** | `conn.log`, `ssl.log`, `weird.log`|
| **Protocols**  | `http.log`, `dns.log`, `ftp.log`  |
| **Detection**  | `notice.log`, `signature.log`     |
| **Observation**| `known_hosts.log`, `software.log` |

## 🔍 Zeek Filtering Tools
Useful command-line tools to analyze Zeek logs:
- `zeek-cut`: Extract specific fields from logs
- `head`: Show first 10 lines (`head -n 10`)
- `tail`: Show last 10 lines (`tail -n 10`)
- `grep 'keyword'`: Filter lines by keyword
- `uniq`: Remove duplicate lines
- `wc -l`: Count number of lines
- `sort`: Sort lines alphabetically

## ✏️ Zeek Signatures
Zeek signatures use pattern matching to detect specific network behaviors or payloads by inspecting packet headers and content.

#### 🔤 General Syntax:
```zeek
signature <signature_id>
{
  ip-proto == <protocol>          # e.g., tcp, udp
  src-ip == <source IP>
  dst-ip == <destination IP>
  payload /<regex-pattern>/       # regex to match in payload
  ftp /<regex>/                   # to match FTP commands
  event "<event name>"            # event triggered
}

## Zeek Scripts
- Zeek scripts are written in an event-driven scripting language designed for network analysis. They are used to:

- Investigate and correlate detected events

- Automate alerting and detection tasks

- Extract valuable data from network traffic

- Scripts can trigger actions when certain conditions are met, enabling real-time threat monitoring and incident response.
