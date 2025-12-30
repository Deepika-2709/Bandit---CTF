# OverTheWire Bandit – Level 22 → Level 23

## 🎯 Level Objective
The goal of **Bandit Level 22 → Level 23** is to retrieve the password for the next level.

In this level:
- You are logged in as **bandit22**
- A cron job runs automatically as **bandit23**
- The cron script dynamically generates a filename
- You must reverse the logic to locate and read the password file

---

## 🖥️ Environment Details
- Wargame: OverTheWire Bandit
- Current User: bandit22
- Target User: bandit23
- SSH Port: 2220
- Mechanism Used: `cron` jobs
- Relevant Directories:
  - `/etc/cron.d`
  - `/usr/bin`
  - `/tmp`

---

## 🔐 Login Command
ssh bandit22@bandit.labs.overthewire.org -p 2220

---

## 🧪 Step-by-Step Solution

### Step 1️⃣ List Cron Jobs
Check the cron jobs directory:

ls /etc/cron.d

Output includes:
cronjob_bandit23

📌 This cron job is responsible for tasks related to bandit23.

---

### Step 2️⃣ Read the Cron Job Configuration
View the cron job file:

cat /etc/cron.d/cronjob_bandit23

Output:
@reboot bandit23 /usr/bin/cronjob_bandit23.sh >/dev/null  
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh >/dev/null

📌 The script runs every minute as **bandit23**.

---

### Step 3️⃣ Inspect the Cron Script
Read the script executed by cron:

cat /usr/bin/cronjob_bandit23.sh

Script logic:
- Determines the username using `whoami`
- Generates a filename by hashing a string with `md5sum`
- Writes the password of bandit23 into a file under `/tmp`

Relevant lines:
- `myname=$(whoami)`
- `mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)`
- Password copied to `/tmp/$mytarget`

---

### Step 4️⃣ Recreate the Target Filename
Since the script runs as **bandit23**, reproduce the hash manually:

echo I am user bandit23 | md5sum | cut -d ' ' -f 1

Output:
8ca319486bfbbc3663ea0fbe81326349

📌 This is the filename used in `/tmp`.

---

### Step 5️⃣ Read the Generated Password File
Read the file created by the cron job:

cat /tmp/8ca319486bfbbc3663ea0fbe81326349

---

### Step 6️⃣ Retrieve the Password
Output displayed:

0Zf11io1iJwN5SijX3CmStKLyqjk54Ga

This is the password for **bandit23**.

---

## 🔐 Password Found
0Zf11io1iJwN5SijX3CmStKLyqjk54Ga

---

## ➡️ Login to Next Level
Use the password above to log in to the next level:

ssh bandit23@bandit.labs.overthewire.org -p 2220

---

## 🖼️ Screenshot Evidence

![Bandit Level 22](screenshot/level22.png)

---

## 📘 Key Concepts Learned
- Advanced cron job analysis
- Understanding dynamic filename generation
- Using hashing (`md5sum`) to trace files
- Reverse-engineering automation scripts
- Privilege separation with scheduled tasks

---

## ✅ Level Status
✔️ Bandit Level 22 → Level 23 completed successfully
