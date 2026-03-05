# 🐧 Linux Privilege Escalation & Log Monitoring Simulation Lab

🗓️ Date: May 2025  
🖥️ Environment: Linux Lab / VM Simulation  
🎯 Focus: Studying privilege escalation vectors and evaluating logging and detection artifacts from a defensive perspective.

---

## 🧠 Lab Overview

This lab explores common Linux privilege escalation scenarios in a controlled environment to understand how attacker techniques appear in system logs and how defenders can detect them.

The objective was not exploitation of real systems, but rather observing how privilege escalation attempts, persistence mechanisms, and log modifications generate detectable artifacts within Linux logging systems.

All testing was conducted in an isolated lab environment.

---

## 🏗️ Lab Environment

The environment consisted of a Linux system configured for testing common privilege escalation scenarios.

The lab involved:

• Reviewing sudo privilege assignments  
• Enumerating SUID binaries  
• Inspecting cron-based scheduled tasks  
• Observing authentication logs  
• Evaluating potential log integrity weaknesses

The goal was to map attacker techniques to observable detection signals.

---

# 🔍 Privilege Escalation Scenario Analysis

## Sudo Configuration Review

Privilege escalation risks were evaluated by inspecting sudo permissions.

Command used:


sudo -l


This allowed identification of commands that may allow elevated execution if misconfigured.

Key concept demonstrated:

• Linux privilege delegation  
• Improper sudo permission assignment risks

---

## SUID Binary Enumeration

SUID binaries were identified using:


find / -perm -4000 2>/dev/null


This command lists executables that run with elevated privileges.

Analysis focused on identifying binaries that could potentially allow privilege escalation if improperly configured.

Concepts demonstrated:

• Execution context awareness  
• Privileged binary behavior

---

## Cron-Based Persistence Review

Scheduled tasks were inspected to understand how automated scripts could maintain persistence within a system.

Files reviewed included:

• `/etc/crontab`  
• user crontabs via `crontab -l`

This helped illustrate how scheduled jobs may be used to maintain recurring execution.

Concept demonstrated:

• Persistence mechanisms within Linux systems

---

# 🛡️ Log Monitoring & Detection Analysis

A key focus of this lab was observing how system activity appears in Linux logs.

Logs reviewed included:

• `/var/log/auth.log`  
• sudo usage records  
• failed authentication attempts

The goal was to identify patterns that security monitoring systems could use to detect suspicious behavior.

Examples of observable signals include:

• repeated failed authentication attempts  
• unusual sudo command execution  
• unexpected scheduled task modifications

---

# 🔬 Log Integrity Observation

The lab also explored how modifications to logs may affect investigation visibility.

Simulated attacker techniques were evaluated to understand how logging artifacts may change and how defenders could identify potential inconsistencies in log data.

This reinforces the importance of centralized logging and monitoring systems.

---

# 📁 Repository Contents

`lab-notes.txt` — documentation of commands used and observations  
`detection-notes.txt` — log analysis observations  
`README.md` — project documentation

---

# 🧰 Skills Demonstrated

• Linux privilege escalation concept analysis  
• sudo permission auditing  
• SUID binary enumeration  
• cron persistence awareness  
• Linux authentication log analysis  
• detection-focused security mindset

---

# 🎯 Learning Outcome

This lab demonstrates how common Linux privilege escalation techniques generate system artifacts and how those artifacts can be analyzed from a security monitoring perspective.

The exercise reinforces how defenders can identify suspicious activity through log inspection and system behavior analysis.

---

# ⚠️ Disclaimer

This project was conducted in a controlled lab environment for educational purposes to study Linux security behavior and detection techniques.