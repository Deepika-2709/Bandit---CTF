# OverTheWire Bandit – Level 16 → Level 17

## 🎯 Level Objective

The objective of **Bandit Level 16 → Level 17** is to retrieve the next level’s password by **connecting to an SSL-enabled service that provides an RSA private key**, which must then be used to log in via SSH.

This level introduces:

* Finding and connecting to an **SSL service**
* Handling **RSA private keys**
* SSH login using **key-based authentication**

---

## 🖥️ Environment Details

* Current User: bandit16
* SSL Port Used: 31790
* Service Type: SSL-enabled service
* Password File: `/etc/bandit_pass/bandit16`

---

## 🔐 Commands Used

```bash
cat /etc/bandit_pass/bandit16 | ncat --ssl localhost 31790
```

```bash
nano key17
```

```bash
chmod 600 key17
```

```bash
ssh -i key17 bandit17@localhost
```

```bash
cat /etc/bandit_pass/bandit17
```

---

## 🔍 Command Breakdown

* `cat /etc/bandit_pass/bandit16`
  → Reads the current level password
* `ncat --ssl localhost 31790`
  → Sends the password securely to the SSL service and receives an RSA private key
* `nano key17`
  → Saves the received RSA private key into a file
* `chmod 600 key17`
  → Secures the private key with proper permissions
* `ssh -i key17 bandit17@localhost`
  → Logs in to bandit17 using the private key
* `cat /etc/bandit_pass/bandit17`
  → Displays the password for the next level

---

## 📤 Output Received

```text
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
```

```text
EReVavePLFHtFlFsjn3hyzMlvsSuSAcRD
```

---

## 🔑 Password for Next Level (Bandit17)

```text
EReVavePLFHtFlFsjn3hyzMlvsSuSAcRD
```

---

## 🖼️ Screenshot Evidence

![Bandit Level 16 Step 1](screenshot/level16_1.png)

![Bandit Level 16 Step 2](screenshot/level16_2.png)

![Bandit Level 16 Step 3](screenshot/level16_3.png)

![Bandit Level 16 Step 4](screenshot/level16_4.png)

---

## 📘 Key Concepts Learned

* Secure communication using **SSL**
* Extracting and handling **RSA private keys**
* Importance of file permissions (`chmod 600`)
* SSH key-based authentication
* Practical use of `ncat` with SSL

---

## ✅ Level Status

✔️ Bandit Level 16 → Level 17 Completed Successfully 
