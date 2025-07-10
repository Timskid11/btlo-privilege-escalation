# btlo-privilege-escalation
Log analysis and privilege escalation challenge from BTLO (Blue Team Labs Online) involving a simulated Linux server compromise and root access via SUID misconfiguration.

# 🔐 BTLO - Log Analysis: Privilege Escalation

**A forensics challenge from Blue Team Labs Online (BTLO)**  
Analyzed logs and command history to trace an attacker's path from web shell to root access via SUID-exploitable Python binary.

## 🧠 Key Learnings
- Web upload bypass using `.phtml`
- Reverse shell injection
- Privilege escalation via misconfigured `python` with SUID bit
- Importance of deeper log review beyond `bash_history`

## 📁 Files
- `writeup.md`: Full explanation of how the attack happened
- `bash_history.txt`: Provided evidence from the challenge
- `screenshots/`: Screenshots of exploitation steps
- `tools-used/`: Relevant scripts or tools used

## 🔗 Challenge Source
[Blue Team Labs Online](https://blueteamlabs.online)

## 👤 Author
[@Timskid11](https://github.com/Timskid11/btlo-privilege-escalation)
