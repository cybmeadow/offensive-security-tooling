# Offensive-security-tooling

In the **Offensive Security Tooling** module! I was able to learn hands-on experience of three powerful penetration testing tools: **Hydra**, **Gobuster**, and **SQLMap**. Each tool targets a different layer of application security — from brute-forcing credentials to uncovering hidden directories and exploiting vulnerable databases.

---

## 🔧 Tools Covered

### 1️⃣ Hydra – Password Brute-Forcing

Hydra is a fast and flexible login cracker that supports numerous protocols including SSH, FTP, HTTP, and more.

**Use Cases:**
- Brute-force SSH, FTP, and web form credentials
- Multi-threaded attacks for speed
- Custom wordlists and username lists

**Example Command:**
```bash
hydra -l user -P /usr/share/wordlists/rockyou.txt ssh://10.10.112.60 -t 4
```

---

### 2️⃣ Gobuster – Directory & File Discovery

Gobuster is a tool used to brute-force URIs (directories and files) on web servers.

**Use Cases:**
- Discover hidden directories and files
- Identify potential entry points for web exploitation
- Supports DNS subdomain enumeration

**Example Command:**
```bash
gobuster dir -u http://10.10.112.60 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

---

### 3️⃣ SQLMap – SQL Injection Automation

SQLMap automates the process of detecting and exploiting SQL injection flaws in web applications.

**Use Cases:**
- Identify SQL injection vulnerabilities
- Extract database contents
- Bypass login forms and escalate privileges

**Example Command:**
```bash
sqlmap -u "http://10.10.112.60/login.php?user=admin" --batch --dbs
```

---

## 🎯 Learning Objectives

- Understand how to use Hydra for credential attacks across multiple protocols
- Discover hidden web directories and files using Gobuster
- Exploit SQL injection vulnerabilities with SQLMap
- Interpret tool output and apply findings to real-world scenarios

---
