# 🔍 Splunk-Free-Installation-and-Ingest-First-Logs


**Author:** Dashane James  
**Lab Environment:** [e.g. VMware Workstation | Kali Linux | Metasploit | Metasploitable 2]  
**Purpose:** 
**Status:** 🟢 Active / 🟡 In Progress / 🔵 Completed

---

## 📋 Overview

[Installed Splunk Free and ingest previous lab scan output files for analysis.]

---

## 🧪 Lab Environment
| Component | Details |
|---|---|
| Hypervisor | VMware Workstation (Host-Only Network) |
| Attacker Machine | Kali Linux 2026.1 — `192.168.79.129` |
| Target Machine | [Metasploitable] — `192.168.79.130` |
| Network Type | Host-Only (isolated, no internet exposure) |
| Host OS | Windows 11 — ASUS Vivobook 14 |

> ⚠️ **Note:** All activity was performed in a controlled, isolated lab environment against deliberately vulnerable machines. No unauthorized access to live networks was performed.

---

## 🛠️ Tools Used

attack.mitre.org 

- **[Metasploit]** — a penetration testing framework that packages known exploits into ready-to-run modules, so you can point one at a vulnerable service and attempt exploitation instead of writing exploit code from scratch.
- **[Metasploitable]** — Acts as a target machine with many intentional vulnerabilities to practice penetration testing, ethical hacking, and securely auditing safely.


---

## 🔬 Tasks / Assessments Performed

###1. Downloaded Splunk Enterprise Free from splunk.com

<img width="671" height="365" alt="Screenshot 2026-09-17 141131" src="https://github.com/user-attachments/assets/ddaeb829-a42e-4d13-883b-6f07d9f21f87" />

<img width="327" height="224" alt="Screenshot 2026-09-17 141205" src="https://github.com/user-attachments/assets/0225e8f9-621a-4000-90de-2af60a4a0942" />

Output explained:

I copied the wget link for the .deb Linux version of Splunk Enterprise Free on the Splunk website. I pasted it into the command prompt and executed it which then downloaded on my Linux device. 
2. [Access Splunk at http://localhost:8000]

<img width="325" height="253" alt="Screenshot 2026-09-17 222727" src="https://github.com/user-attachments/assets/44a0f2ea-7d60-4087-b040-d5f9437ef2fd" />

<img width="329" height="257" alt="Screenshot 2026-09-17 222555" src="https://github.com/user-attachments/assets/80443ee6-dbee-4d9e-9ae3-014e6c586a0b" />

<img width="851" height="373" alt="Screenshot 2026-09-17 150533" src="https://github.com/user-attachments/assets/6e8ca33a-757f-4bd2-8bc4-a1d97c03ad4d" />


Output explained:

After downloading Splunk, I ran sudo dpkg -i to install it and sudo /opt/splunk/bin/splunk start --accept-license --run-as-root to launch it, which established a local host connection accessible in the web browser at http://127.0.0.1:8000. The webpage is then successfully accessed in the last screen shot.

3. [Settings > Data Inputs > Upload your NMAP output files from previous tasks.]

<img width="650" height="293" alt="Screenshot 2026-09-17 154617" src="https://github.com/user-attachments/assets/2972b744-7343-4102-8989-e835ae6b89f3" />


<img width="650" height="293" alt="Screenshot 2026-09-17 154617" src="https://github.com/user-attachments/assets/e477e6be-d18e-4da0-a652-53122566f8b2" 

<img width="805" height="338" alt="Screenshot 2026-09-17 154915" src="https://github.com/user-attachments/assets/0b22ec2a-403b-454a-a1eb-96a292fb446b" />


Output explained:

For this task I clicked on the add data tab located on the Splunk Enterprise homepage and uploaded the targeted Nmap file that I saved to a file back in my previous task in the first repository, "nmap_services.txt". Next, Splunk then ran a search to verify the data was ingested correctly. The search returned two events from this nmap_services.txt file. The first event shows the scan summary (1 IP address scanned, host is up), and the second shows the full scan initiation including the exact command used, the target IP, and the open ports with their services and versions. This confirms Splunk successfully parsed and indexed the Nmap output file, making the scan data searchable within the SIEM. 

4. [Run a basic search: index=main]

<img width="853" height="322" alt="Screenshot 2026-09-17 155300" src="https://github.com/user-attachments/assets/991c14a3-cee1-403e-8158-4f5f304f38fd" />

Output explained: I ran a basic search of index=main, which means "show me everything you have stored". Since this was the only file stored in the folder, it showed the same output as when this specific file "nmap_services.txt" was searched for in the previous task. 

  5. [Create a simple dashboard showing event counts.]

<img width="854" height="336" alt="Screenshot 2026-09-17 155416" src="https://github.com/user-attachments/assets/87e5a452-65ff-4859-b395-7af330bd7e90" />

Output explained:





📊 Key Findings Summary
Port/Service	Tool Used	Risk Level	Notes
[e.g. 21/tcp FTP]	[e.g. Nmap]	🔴 Critical	[Notes]
[e.g. 23/tcp Telnet]	[e.g. Wireshark]	🔴 Critical	[Notes]
[e.g. 80/tcp HTTP]	[e.g. Nikto]	🟠 High	[Notes]
[e.g. 3306/tcp MySQL]	[e.g. OpenVAS]	🟠 High	[Notes]
[e.g. 22/tcp SSH]	[e.g. Nmap]	🟡 Medium	[Notes]


Risk Levels: 🔴 Critical | 🟠 High | 🟡 Medium | 🟢 Low

🗺️ MITRE ATT&CK Mapping
Action Performed	ATT&CK Tactic	Technique ID	Technique Name
[e.g. Port scanning]	[e.g. Reconnaissance]	[e.g. T1595]	[e.g. Active Scanning]
[Action]	[Tactic]	[ID]	[Technique]
[Action]	[Tactic]	[ID]	[Technique]
[Action]	[Tactic]	[ID]	[Technique]
🛡️ Defensive Recommendations
Based on findings, the following remediations would be recommended in a real environment:

[Finding 1] — [Recommendation]
[Finding 2] — [Recommendation]
[Finding 3] — [Recommendation]
[Finding 4] — [Recommendation]
[Finding 5] — [Recommendation]
📚 CySA+ Exam Relevance
This lab directly maps to the following CompTIA CySA+ (CS0-003) exam domains:

Domain	Coverage
Security Operations (33%)	[What this lab covers in this domain]
Vulnerability Management (30%)	[What this lab covers in this domain]
Incident Response (20%)	[What this lab covers in this domain]
Reporting & Communication (17%)	[What this lab covers in this domain]
🔑 Technical Notes
[Any important notes about your lab setup, workarounds, or lessons learned. Example:

Enumeration

The outline for MITRE ATT&CK's own structure is Tactic > Technique > Sub-Technique

(STEP 1: Describe the action in plain english) :
STEP 2:  Identify the tactic/goal
STEP 3: Find the technique within the section of the specified tactic/goal
STEP 4: Check for a sub-technique
STEP 5: Verify


# Any important commands or workarounds
[command here]
shell 

📌 About This Project
[1-2 sentences about how this fits into your overall portfolio and career goals.]

Related repositories:

[Repo Name] — [Brief description]
[Repo Name] — [Brief description]
[Repo Name] — Coming soon
👤 Author
Dashane James
Senior Field Service Technician → Cybersecurity Analyst
📍 Yonkers, NY
🎓 B.S. Information Technology — SUNY Canton
🏆 CompTIA Security+ | CySA+ (In Progress)
🔗 GitHub | Zero Trust Cyber Security Brand

This repository is part of an active portfolio demonstrating hands-on cybersecurity skills. All lab work performed in isolated environments for educational purposes.
