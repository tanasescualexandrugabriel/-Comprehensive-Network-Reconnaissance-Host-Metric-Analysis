# -Comprehensive-Network-Reconnaissance-Host-Metric-Analysis
**Lab Executed and Documented Entirely by: @tanasescualexandrugabriel**
This repository documents the complete network security audit, perimeter mapping, and advanced cryptographic stack analysis that **I have personally executed**. Using progressive scanning layers inside the Zenmap ecosystem, I targeted the authorized host `scanme.nmap.org`. This multi-phased project tracks my progression from rapid open-port discovery to deep-dive host metric inspection, covering operating system classes, packet sequencing, and active firewall behaviors.

---

## 1. Step-by-Step Lab Execution History

To successfully complete this security project, I manually executed the following procedural pipeline inside the Zenmap application:
1. **Phase 1 Execution (Quick Scan):** I launched Zenmap, entered `scanme.nmap.org` into the Target field, and selected the rapid profiling layout to discover basic exposed perimeter assets within seconds.
2. **Phase 2 Configuration (Aggressive Scan):** To gather deeper metrics, I modified my Target string to append my custom identifier (`scanme.nmap.org scan by @tanasescualexandrugabriel`) and initialized an aggressive engine sweep (`-T4 -A -v`) to force banner grabbing and traceroute routing.
3. **Host Details Investigation:** Once the active engine threads completed, I navigated directly to the **Host Details** tab interface window.
4. **Deep Contextual Scrolling:** I systematically scrolled through the sub-panels to capture precise hardware indicators, packet sequence predictability logs, and specific fingerprinting validation points.

---

## 2. Phase 1: Rapid Perimeter Reconnaissance (Quick Scan)

In the initial stage of my lab, I executed a lightweight scan to quickly map out accessible ports visible from the external perimeter before launching noisier queries.

* **My Executed Command:** `nmap -T4 -F scanme.nmap.org`

### My Technical Observations (Phase 1):
* **High Efficiency:** The scan was completed in just **2.65 seconds** because the `-F` (Fast) flag limited the testing pool exclusively to the top 100 most common TCP ports.
* **Port Discovery Baseline:** The target immediately responded with **97 closed TCP ports** (via explicit reset packets). Port **22/tcp (ssh)** and port **80/tcp (http)** were found completely **open**, while port **25/tcp (smtp)** showed early signs of being **filtered** by an upstream firewall.

---

## 3. Phase 2: Aggressive Scanning and Active Service Discovery

Next, I escalated the audit into an intense inspection (`Aggressive Scan`) to force the remote applications to reveal their version details, active system layers, and routing sequences.

* **My Custom Command Line:** `nmap -T4 -A -v scanme.nmap.org scan by @tanasescualexandrugabriel`

### My Technical Observations (Phase 2):
* **Verbose Feedback Mode (`-v`):** By including the verbose parameter, Nmap immediately displayed discovered open connections live as they happened, rather than forcing me to sit through the entire engine execution runtime.
* **Script Pre-Scanning Activity:** I monitored the engine loading a comprehensive suite of 158 automated Nmap Scripting Engine (`NSE`) scripts designed to probe for configuration flaws on the host.

---

## 4. Deep Service Interpretation and Banner Grabbing Analysis

Once my aggressive thread finished scanning the top 1000 standard ports, I scrutinized the resulting logs to map out the state and specific software versions running behind each port.

### Technical Analysis of My Port Map Table:

| Port | Protocol | State | Service | Version / Banner Captured | Technical Explanation & Security Assessment |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **22** | TCP | **open** | ssh | OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 | **Open:** Remote command-line administration is active. My probe successfully pulled the application banner, which leaks that the target infrastructure runs an underlying **Ubuntu Linux** operating system distribution. |
| **25** | TCP | **filtered** | smtp | Unknown | **Filtered:** This standard mail delivery socket is actively protected by a firewall policy, which drops packets silently and prevents Nmap from discovering if it is physically open or closed. |
| **80** | TCP | **filtered** | http | Unknown | **Filtered:** The web port transitioned from *open* (in Phase 1) to *filtered* here. This clearly proves that the server's defensive mechanisms dynamically reacted to my rapid, consecutive scanning behavior and blocked my IP address. |
| **9929** | TCP | **open** | nping-echo | Nping echo | **Open:** A dedicated port utilized by the Nping packet generator module. It echoes back test data streams to measure network performance, packet modifications, and round-trip delay. |
| **31337** | TCP | **open** | Elite | tcpwrapped | **Open (Protected):** Returned as `tcpwrapped`. This demonstrates that my system completed a standard 3-way TCP handshake, but an internal application-layer protection tool cut the connection immediately before any data payloads could be exchanged. |

---

## 5. Host Network Identification & Addressing Layout
I inspected the network layer components to verify routing names and address assignments pointing to the target infrastructure:
* **Target IPv4 Coordinates:** `45.33.32.156`
* **Target IPv6 Availability:** Not available / Not exposed during this probe thread.
* **Hardware MAC Address:** Not available (indicates the target resides outside my local broadcast domain and was analyzed over layer-3 wide area networks).
* **Domain Name System (DNS) Mapping:** Validated the fully qualified domain name as `scanme.nmap.org` with an active reverse pointer (**PTR Type**) record resolved to the same domain namespace.

---

## 6. Operating System (OS) Classes & Fingerprint Accuracy
By directing Nmap to cross-reference packet response anomalies against its local signatures database, I isolated the precise engineering specifications of the target:
* **Device Vendor Classification:** Generic Linux computer architecture.
* **OS Family & Generation:** Restricted to the **Linux 4.X** deployment category.
* **Detected Operating System Kernel Range:** Confirmed to be running within the `Linux 4.19 - 5.15` release tier.
* **System Uptime Tracking:** The remote operating system stack logged an uptime metrics count of `2187305`. This establishes that the target machine has been continuously operating without a single system reboot or kernel reload since **Thursday, June 18, 23:30:00, 2026**.

---

## 7. OS Fingerprinting Verification Criteria (Ports Used)
To successfully determine the exact operating system build above, I monitored the Nmap engine selecting and testing against three very specific, distinct port states to map stack responses:
1. **Port 22 (TCP):** Utilized as the open validation reference socket state (`Protocol: tcp | State: open`).
2. **Port 1 (TCP):** Utilized as the closed verification reference socket state (`Protocol: tcp | State: closed`).
3. **Port 35253 (UDP):** Utilized as the closed User Datagram Protocol verification reference socket state (`Protocol: udp | State: closed`).

---

## 8. TCP/IP Protocol Stack Sequencing Analysis
I conducted a granular review of the host's network stack predictability. Analyzing these metrics is critical during a security assessment to ensure the system is resilient against advanced attacks like TCP sequence prediction or blind connection hijacking:

* **TCP Sequence Difficulty:** Logged an overall difficulty index tier of `258`. The engine flags this specific metric score as **"Good luck!"**, meaning the sequence numbers generated by the remote kernel are highly randomized and mathematically difficult for an attacker to spoof.
* **TCP Sequence Hexadecimal Value:** Captured the precise sequence metric validation window state at `7AD1BAAB`.
* **IP ID Sequence Generation Class:** Identified as **All zeros**, which is typical for modern, secure Linux kernels that drop sequential IP ID increments to mitigate information leakage and host tracking over the web.
* **IP ID Value Status:** Checked and registered at a static base tier of `0`.
* **TCP TS (Timestamp) Sequence Class:** Categorized as **1000HZ**, reflecting standard system clock updates at 1 millisecond intervals.
* **TCP TS Value State:** Measured and logged at hexadecimal parameter value `825F79AE`.

---

## My Final Security Conclusions and Key Takeaways
1. **Dynamic Firewall Resilience:** This lab explicitly taught me how active network defenses change rules on the fly (such as Port 80 dropping into a `filtered` state after detecting aggressive repetitive traffic patterns).
2. **Information Disclosure Risks:** The target server openly discloses its software version (`OpenSSH 6.6.1p1`). In a real security audit, this represents a notable risk, as a malicious actor could immediately search vulnerability databases for public exploits targeting this specific release.
3. **Predictability Resilience:** The TCP Sequence difficulty ranking (`258 / Good luck!`) proves the target operating system uses an excellent, secure pseudo-random number generator (PRNG). This effectively prevents attackers from guessing sequence numbers to inject malicious payloads into open connections.
4. **Defensive Kernel Hardening:** Operating on a lean Linux 4.X release architecture with strict IP ID generation handling (**All zeros**) shows a hardened network stack configuration optimized to block behavioral host tracking and identification analysis.

