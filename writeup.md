# 🔐 BTLO - Log Analysis: Privilege Escalation

## 🧠 Scenario Summary

A server hosting sensitive data was breached. The attacker escalated privileges from a restricted web user (`www-data`) to `root` and exfiltrated data that was later leaked online. The system administrator claimed that proper upload filtering was in place and the bash history file appeared clean. My task was to analyze the evidence and determine **what really happened**.

---

## 🕵️ Findings & Analysis

### 1️⃣ Initial Access

- The attacker likely gained access through a **PHP-based file upload bypass**.
- The upload filter did not allow `.php` files, but the attacker uploaded a **`.phtml`** file, which is still interpreted as PHP by the server.

> ✅ **File Extension Used:** `.phtml`

---

### 2️⃣ Reconnaissance & Exploitation

- After gaining a web shell, the attacker downloaded `linux-exploit-suggester.sh` — a tool used to identify possible privilege escalation vectors on Linux systems.

> ✅ **Script Used:** `linux-exploit-suggester.sh`

- They also attempted to use **`tcpdump`**, a network packet analysis tool, likely to monitor traffic or capture sensitive credentials.

> ✅ **Packet Analyzer Tool:** `tcpdump`

---

### 3️⃣ Privilege Escalation

- The attacker discovered that the `python` binary had the **SUID (Set User ID)** permission bit set, allowing it to execute with elevated privileges.

- Using this misconfiguration, the attacker executed a simple Python command to spawn a root shell:

```bash
python -c 'import os; os.setuid(0); os.system("/bin/bash")'
