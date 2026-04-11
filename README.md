# 🔍 SOC Project 5 — Incident Investigation (Brute Force Attack)

## 📌 Objective
Investigate Windows login logs to detect brute force attack using Splunk.

---

## 🧰 Tools Used
- Splunk Enterprise
- Windows Event Viewer

---

## 🔍 Logs Used
- Event ID 4625 → Failed login
- Event ID 4624 → Successful login

---

## 🚨 Detection Logic
(EventCode=4624 OR EventCode=4625)
| eval user=TargetUserName
| stats count(eval(EventCode=4625)) as failed count(eval(EventCode=4624)) as success by user
| where failed > 2 AND success > 0


---

## 📊 Findings

- User: yash
- Failed Attempts: 4+
- Successful Login: Yes
- Time Gap: Few seconds

---

## 🧠 Conclusion

Multiple failed login attempts followed by successful login indicate a **brute force attack**.

---

## 🚨 Alert Created

- Type: Scheduled
- Cron: */5 * * * *
- Trigger: Results > 0
- Severity: Medium

---

## 📸 Screenshots

(Add your Splunk screenshots here)

---

## 🎯 Skills Gained

- Windows log analysis
- Splunk SPL queries
- Brute force detection
- Alert creation
- Incident investigation