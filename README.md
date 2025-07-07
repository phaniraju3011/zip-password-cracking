# 🔐 ZIP Password Cracking Lab: Demonstrating Password Policies

![Terminal Screenshot](https://github.com/user-attachments/assets/6ae604e9-4080-478a-829b-136d3d97b39c)

---

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
🔐 Step 2: Extract Hash from ZIP
bash
Copy
Edit
zip2john protected.zip > sample.zip.john
🚀 Step 3: Crack the Password with John the Ripper
bash
Copy
Edit
john --wordlist=/usr/share/wordlists/rockyou.txt sample.zip.john
👀 Step 4: View the Cracked Password
bash
Copy
Edit
john --show sample.zip.john




5. 🔍 Understanding Weak vs. Strong Password Policies
🔻 Weak Password Policies
Common Characteristics:

Short passwords (e.g., under 8 characters)

Use of common or predictable words: password, 123456, qwerty

Keyboard patterns or sequences: abc123, letmein, password1

Lack of complexity (only lowercase or numbers)

Personal information (e.g., pet names, birthdays)

Examples of Weak Passwords:

password

12345678

admin

welcome

letmein

Risks:

✅ Easily guessed or cracked by attackers

✅ Frequently found in breached password dumps

✅ Often reused across multiple sites

✅ Susceptible to brute-force and dictionary attacks

✅ Strong Password Policies
Strong Password Characteristics:

Minimum of 12–16 characters

Mix of uppercase, lowercase, numbers, and special characters

No dictionary words or predictable patterns

Unique for every service/account

Avoids personal information

Examples of Strong Passwords:

G7$k9@Lm2PqR

Tb9#zX1vW2mN

C0mpl3xP@ss!234

Randomly generated via password manager

🛡️ Best Practices
Practice	Description
🔐 Minimum Length	Enforce at least 12–16 characters
⚙️ Character Diversity	Require uppercase, lowercase, digits, and symbols
🧠 User Education	Train users to build and recognize strong passwords
🧾 Regex Enforcement	Example:
^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&]).{12,}$
🔄 Rotation (if needed)	Periodic updates may help in sensitive environments
🔑 Use MFA	Add Multi-Factor Authentication as an extra layer
💼 Password Managers	Encourage tools like Bitwarden, 1Password, or KeePass

🧪 Example Scenario
Scenario	Password	Result
Weak Policy	password123	✅ Cracked in seconds
Strong Policy	G7$k9@Lm2PqR	❌ Not cracked

🧠 Conclusion
This lab reinforces the importance of strong password policies:

Weak passwords like password123 can be cracked instantly, even with basic tools.

Strong, random passwords like G7$k9@Lm2PqR resist cracking attempts, even when known tools and dictionaries are used.

Organizations should enforce length, complexity, and uniqueness, along with MFA and user training, to truly protect data.

🚫 Weak passwords are no match for modern cracking tools. Prevention starts with policy.
