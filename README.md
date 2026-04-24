# <img src="https://cdn.simpleicons.org/owasp/3399CC" height="32" align="center" /> OWASP ZAP Security Scan — manuelaklenke.com

Automated security scan for [manuelaklenke.com](https://manuelaklenke.com) using OWASP ZAP. Runs a full active + passive scan on demand or on a nightly schedule and publishes the report to GitHub Pages.

---

## 📊 Security Report

Latest report: **[https://georget88.github.io/manuelaklenke-owasp-zap-security/](https://georget88.github.io/manuelaklenke-owasp-zap-security/)**

---

## 🛠️ Tech Stack

- [OWASP ZAP](https://www.zaproxy.org/) — web application security scanner
- [zaproxy/action-full-scan](https://github.com/zaproxy/action-full-scan) — official ZAP GitHub Action
- GitHub Actions — CI/CD pipeline
- GitHub Pages — HTML report hosting

---

## 🔍 What Gets Scanned

ZAP full scan covers both passive and active testing:

| Category | Examples |
|---|---|
| Injection | SQL injection, command injection |
| XSS | Reflected, stored, DOM-based |
| Security headers | CSP, HSTS, X-Frame-Options, etc. |
| Authentication | Session management, cookie flags |
| Information disclosure | Server banners, error messages |
| CSRF | Cross-site request forgery |
| Broken access control | Directory traversal, forced browsing |

---

## ⚙️ CI/CD Pipeline

ZAP is **not** triggered on every deployment — active scanning generates significant traffic and takes up to 60 minutes. Instead it runs on a nightly schedule or manually on demand.

It appears as a skipped (grey) box in the [manuelaklenke-web](https://github.com/GeorgeT88/manuelaklenke-web) CI pipeline for visibility, but does not auto-execute.

```
🔍 ZAP full scan against https://manuelaklenke.com
        ↓
📊 HTML report published to GitHub Pages
```

Trigger manually from **Actions → OWASP ZAP Security Scan → Run workflow**, or wait for the nightly schedule at **07:00 UTC**.

---

## 🏷️ Run Name Convention

| Trigger | Run name |
|---|---|
| Manual | `OWASP ZAP Security Scan — manual run` |
| Nightly schedule (07:00 UTC) | `OWASP ZAP Security Scan — nightly run` |
