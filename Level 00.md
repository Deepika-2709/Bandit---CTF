# Bandit Level 0

## 🔐 Access
Bandit Level 0 is the introductory level of the OverTheWire Bandit CTF.  
This level focuses on establishing an SSH connection to the Bandit server.

---

## 🔗 Connection Details
- **Username:** bandit0  
- **Host:** bandit.labs.overthewire.org  
- **Port:** 2220  
- **Password:** bandit0  

---

## 📌 Overview
After logging in successfully, a file named `readme` is present in the home directory.  
This file contains the password required to proceed to **Bandit Level 1**.

---

## 🎯 Objective
- Gain access to the Bandit server
- Locate the password file
- Read the file to obtain the next level password

---

## 🖼️ Screenshot Location
`screenshots/level00.png`

---

## 🛠️ Commands Used
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
ls
cat readme
