# 📄 Incident Report — Brute Force Attack

## 1. Summary
Suspicious login activity detected for user "yash".

---

## 2. What Happened
Multiple failed login attempts were followed by a successful login.

---

## 3. Logs Observed
- Event ID 4625 → Failed login
- Event ID 4624 → Successful login

---

## 4. Indicators
- User: yash
- Multiple failed attempts
- Rapid login attempts

---

## 5. Analysis
This pattern indicates a brute force attack where attacker tried multiple passwords and succeeded.

---

## 6. Mitigation
- Reset user password
- Monitor account activity
- Enable strong password policy