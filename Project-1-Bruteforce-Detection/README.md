# Project 1 – Brute-Force Attack Detection (SIEM Log Analysis)

## 📌 Objective  
Detect brute-force login attempts using log analysis techniques similar to what SOC analysts do.

---

## 🛠️ Tools Used  
- Splunk / Elastic / Wazuh / Any SIEM (or simulated logs)
- Kali Linux / Ubuntu logs (simulated)
- Python (optional)

---

## 🔍 Steps Performed  

### **1. Collected Authentication Logs**
Used sample authentication logs containing:
- Username attempts  
- Source IP addresses  
- Timestamps  
- Status (Success/Failure)

### **2. Loaded Logs into SIEM**
Imported logs into a SIEM dashboard to visualize patterns.

### **3. Created Detection Query**
The rule identifies:
- Multiple failed login attempts  
- From the same IP  
- Within a short time window  

Simulation example:

index=auth-log action=fail
|stats count by src_ip, user
|where count > 5

### **4. Findings**

- IP `192.168.x.x` attempted **15 failed logins** within 2 minutes.  
- Same IP later attempted different usernames (password spraying).  
- No successful login recorded.

### **5. Mitigation**
- Blocked the offending IP address.  
- Recommended enforcing:
  - Multi-factor authentication  
  - Strong password policy  
  - Login rate limiting  

---

## 📁 Files Included  
- sample-auth-logs.csv (simulated log file)
- detection-query.txt (SIEM search rule)

---

## ✔️ Outcome  
Successfully detected a brute-force attack pattern and created a repeatable SIEM detection method.

