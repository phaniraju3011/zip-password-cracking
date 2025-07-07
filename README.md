# 🔐 ZIP Password Cracking Lab: Demonstrating Password Policies

![Terminal Screenshot] ![Screenshot_2025-07-07_08_05_32](https://github.com/user-attachments/assets/6ae604e9-4080-478a-829b-136d3d97b39c)


## 1. 🎯 Project Goal

This project demonstrates the process of cracking password-protected ZIP files using a **dictionary attack** with **John the Ripper**. It highlights how weak password policies make data vulnerable and emphasizes the value of strong passwords in real-world scenarios.

> **Note**: This project is for **educational purposes only**.

---

## 2. 📘 What I Learned

- **ZIP File Security**: How ZIP files implement password protection.
- **Password Cracking Techniques**: Used `zip2john` to extract crackable hash data.
- **Dictionary Attacks**: Learned the power and limitation of using `rockyou.txt`.
- **Security Policies**: Understood the role of password complexity in defense.

---

## 3. 🛠️ Tools and Technologies Used

- **OS**: Kali Linux / Ubuntu
- **Cracking Tool**: [John the Ripper](https://www.openwall.com/john/)
- **Wordlist**: `rockyou.txt` (commonly used password list)
- **Utilities**:
  - `zip` (to create protected ZIPs)
  - `zip2john` (to extract hashes from ZIP)
  - `john` (to perform the actual cracking)

---

## 4. 🔬 Process and Methodology

### 🧾 Step 1: Create a ZIP File with a Password

```bash
echo "This is a secret file." > secret1.txt
echo "Another secret." > secret2.txt
zip --password password123 protected.zip secret1.txt secret2.txt
