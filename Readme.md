### Task 1: Local Network Port Scanning
---
### Tools Used

***Nmap (v7.97):*** Used for port scanning the local network.
***Wireshark:*** Used to capture and analyze network traffic during the scan.

---
### Process

-Installed Nmap from https://nmap.org/.
-Determined my local network IP range (192.168.29.0/24) using **ipconfig** on Windows.
-Executed an Nmap TCP SYN scan with the following command : ```nmap -sS 192.168.29.0/24 -oN scan_result.txt```
-Reviewed the scan results to identify active hosts, open ports, and running services.
-Captured network traffic with Wireshark during the scan to validate findings.
-Researched the identified services to evaluate their security implications.
-Documented the process, results, and insights in this README and supporting files.

---
### Findings
The Nmap scan identified 6 active hosts on the network. Below are the key results:

**192.168.29.1 (Router - reliance.reliance):**
***Open Ports***: 80 (http), 443 (https), 1900 (upnp), 7443 (oracleas-https), 8080 (http-proxy), 8443 (https-alt)
***Closed Ports***: 2869 (icslap), 8002 (teradataordbms), 8200 (trivnet1)
***MAC Address***: F0:ED:B8:59:5C:17 (Servercom (India) Private Limited)


**192.168.29.54:**
***Filtered Port***: 5060 (sip)
***MAC Address***: EE:37:E7:0F:51:8F (Unknown)


**192.168.29.56:**
***All 1000 scanned ports closed***
***MAC Address***: 72:BA:BF:FC:AD:B2 (Unknown)


**192.168.29.198:**
***All 1000 scanned ports closed***
***MAC Address:*** 86:82:6F:00:FC:BA (Unknown)


**192.168.29.209:**
***Filtered Port:*** 5060 (sip)
***MAC Address:*** 90:78:B2:BC:59:11 (Xiaomi Communications)


**192.168.29.68 (Windows Device):**
***Open Ports:*** 135 (msrpc), 139 (netbios-ssn), 445 (microsoft-ds)


---
### Security Insights

**Potential Risks:**
***Router (192.168.29.1):*** Open ports like 1900 (UPnP) could allow unauthorized access or device exploitation if not secured.
***Windows Device (192.168.29.68):*** Ports 135, 139, and 445 are commonly targeted by malware (e.g., ransomware) and should be restricted.


---
### Wireshark Analysis

Captured packets during the Nmap scan to observe network behavior.

***Observations:***
SYN packets were sent to target ports, with SYN-ACK responses indicating open ports and RST responses for closed ports.
Validated Nmap results and provided insight into the scanning process.

---
### Files Included

**scan_result.txt:** Raw output from the Nmap scan.
**Photos:** scanned results of NMAP and wireshark
**README.md:** This documentation file.
**.gitignore:** Excludes Wireshark capture files (e.g., *.pcap, *.pcapng).

---
### Resources
***Nmap documentation (https://nmap.org/docs.html), Wireshark user guide (https://www.wireshark.org/docs/), and online tutorials.***

***Note: Wireshark capture files are excluded via .gitignore due to their size and potential sensitivity. The analysis summary is included above.***

---