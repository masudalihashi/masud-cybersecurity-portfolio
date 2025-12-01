# Project 2: Windows Failed Login Detection (Event Log Analysis)

### 🔍 Objective
Analyze Windows Security Event Logs to detect repeated failed login attempts that may indicate:
- Brute-force attacks
- Unauthorized access attempts
- Compromised accounts

---

## 🖥️ Scenario
A Windows workstation is reporting multiple failed login attempts.  
Your task is to investigate the logs, identify suspicious activity, and determine the source.

---

## 📂 Steps Performed

### **1️⃣ Opened Windows Event Viewer**
- Navigated to `Windows Logs` → `Security`
- Filtered by **Event ID 4625** (failed login)

### **2️⃣ Identified Key Fields**
For every failed attempt, I analyzed:
- **Account Name** (target username)
- **Source IP Address**
- **Failure Reason**
- **Logon Type**

### **3️⃣ Detected Suspicious Patterns**
Looked for:
- Many failures from the same IP  
- Many failures for the same account  
- Failure every few seconds (sign of brute-force)  
- Off-hours activity (midnight, early morning)
Analyzed the output manually.

---

## 📊 Findings
- High number of failed logins for user: **Administrator**
- Attempts happening every 30 seconds (brute-force pattern)
- Source IP: **192.168.1.55**
- Logon Type: **3 (Network)** → Indicates remote login attempts
- Failure Reason: **Bad password**

---

## 🛡️ Security Recommendations
✔ Block the suspicious IP  
✔ Enforce strong password policy  
✔ Enable account lockout policy  
✔ Monitor for successful login after failed attempts  
✔ Enable multi-factor authentication (MFA)

---

## 📝 Skills Demonstrated
- Event Viewer analysis  
- PowerShell log extraction  
- Brute-force detection  
- Windows security investigation  
- SOC analyst reporting  

- 

### **4️⃣ Used PowerShell to Count Login Failures**

