# OverTheWire Bandit – Level 17 → Level 18

## 🎯 Level Objective
The objective of **Bandit Level 17 → Level 18** is to retrieve the next level’s password by **connecting to a local service that provides a passphrase-protected SSH private key**, then using that key to log in via SSH.

This level introduces:
- Handling **passphrase-protected SSH keys**
- Secure **key-based SSH authentication**
- Proper **file permission management**

---

## 🖥️ Environment Details
- Current User: bandit17  
- Target Port: 32256  
- Service Type: Passphrase-protected SSH key service  
- Password File: `/etc/bandit_pass/bandit17`

---

## 🔐 Commands Used
```bash
cat /etc/bandit_pass/bandit17 | ncat localhost 32256
nano key18
chmod 600 key18
ssh -i key18 bandit18@localhost
cat /etc/bandit_pass/bandit18

---

## 📤Output Received

-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----

Th1s1sTh3N3xtP4ssw0rdF0rB4ndit18

---

🔑 Password for Next Level (Bandit18)
Th1s1sTh3N3xtP4ssw0rdF0rB4ndit18

🖼️ Screenshot Evidence

