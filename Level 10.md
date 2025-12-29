# OverTheWire Bandit – Level 10 → Level 11

## 🎯 Level Objective
The goal of **Bandit Level 10 → Level 11** is to find the password for the next level.  
The password is stored in the file `data.txt` and is **base64 encoded**.

You must decode the file to reveal the actual password.

---

## 🖥️ Environment Details
- Wargame: OverTheWire Bandit
- Current User: bandit10
- SSH Port: 2220
- Home Directory File: `data.txt`

---

## 🔐 Login Command
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

---

## 🧪 Commands Used

### 1️⃣ List files in the home directory
```bash
ls
```

**Output:**
```text
data.txt
```

📌 Confirms the file containing the encoded password.

---

### 2️⃣ View the encoded content
```bash
cat data.txt
```

**Output:**
```text
(base64 encoded text)
```

📌 The content is not readable directly, indicating encoding.

---

### 3️⃣ Decode the base64 content
```bash
cat data.txt | base64 --decode
```

**Explanation:**
- `base64 --decode` converts base64-encoded data back into readable text
- The decoded output reveals the password for the next level

---

## 🔐 Password Found
```text
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## ➡️ Login to Next Level
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

---

## 🖼️ Screenshot Evidence
![Bandit Level 10 Screenshot](screenshot/level10.png)

---

## 📘 Key Concepts Learned
- Understanding base64 encoding
- Decoding encoded files using Linux tools
- Using pipelines (`|`) to process file data
- Identifying encoded vs plain-text content

---

## ✅ Level Status
✔️ Bandit Level 10 → Level 11 Completed Succ
