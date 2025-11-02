

# 💳 Secure FinTech Web App (Streamlit + Ngrok + Colab)

This project is a **secure FinTech mini-application** developed in **Python**, **Streamlit**, and **Google Colab**.  
It demonstrates secure login, encryption, transaction handling, and activity logging — ideal for cybersecurity testing and demonstrations.

---

## Features

### Core Functionality
- **User Registration & Login**
  - Validates strong passwords
  - Prevents weak or duplicate usernames
  - Hashes passwords securely (no plaintext)
- **Session Management**
  - Auto logout after 5 minutes idle
- **Transaction Management**
  - Submit valid transactions with amount, recipient, and description
  - Validate inputs and reject invalid entries
- **Encryption / Decryption**
  - Uses `cryptography.fernet` for secure symmetric encryption
- **Activity Logs**
  - Logs all major actions: register, login, logout, transactions, errors, etc.
- **Error Handling**
  - Custom `safe_run()` wrapper catches and logs internal errors safely
- **SQL Injection & XSS Prevention**
  - Inputs are sanitized and validated

---

## Developer Info
**Shaheer — Roll: 12345 — Course: Cyber Security 101**

---

## Security Test Cases

| # | Test Case | Expected Result |
|---|------------|----------------|
| 1 | Register with valid username and strong password | ✅ Registered successfully |
| 2 | Weak password (`12345`) | ⚠️ Rejected with warning |
| 3 | Register existing username | ❌ Error: “Username exists” |
| 4 | Username with spaces or symbols | ⚠️ Rejected |
| 5 | Correct username/password login | ✅ Welcome message |
| 6 | Wrong credentials | ❌ “Invalid login” |
| 7 | Idle > 5 min | ⏱ Auto logout |
| 8 | Logout click | ✅ Session cleared |
| 9 | Valid transaction | ✅ Stored & confirmed |
| 10 | Invalid amount or empty recipient | ⚠️ Warning shown |
| 11 | Open “Activity Logs” page | 📋 Shows chronological log |
| 12 | Encrypt text | 🔐 Ciphertext displayed |
| 13 | Decrypt text | 🔓 Original text recovered |
| 14 | Force error (divide by zero) | ⚠️ Generic error logged |
| 15 | Inspect password in DB | 🔒 Hashed value only |
| 16 | Check `fernet.key` | ✅ Exists separately |
| 17 | SQL injection attempt | 🚫 Blocked safely |
| 18 | HTML/JS in text field | 🧼 Sanitized (no execution) |
| 19 | Review activity logs | 📖 Complete & untampered |
| 20 | Verify name, roll #, course info | ✅ Displayed correctly |

---

## 🛠️ Technologies Used
- **Python 3.10+**
- **Streamlit**
- **PyNgrok**
- **Cryptography (Fernet)**
- **SQLite3**
- **Google Colab**

---

## 🧑‍💻 Running in Google Colab

1. **Upload** the provided `.ipynb` file to Google Colab.  
2. **Run cells** sequentially:
   - Install dependencies
   - Write app files (`app_logic.py`, `app_streamlit.py`)
   - Start Streamlit and Ngrok
3. Paste your **Ngrok authtoken** when prompted.
4. Wait for a **Public URL** (displayed as `https://xxxx.ngrok-free.dev`).
5. Click the link to access your running Streamlit web app.
6. To stop, click the **Stop** button in Colab or `Runtime → Restart runtime`.

---

## 📂 Project Structure

