# EFS Evaluation Framework – Success Metrics & Validation  

---

## 1. QUICK SUCCESS DASHBOARD (Live KPIs)

| Metric | Target | Current | Status |
|--------|--------|--------|--------|
| **Login Success Rate** | ≥ 98% | `{{LOGIN_RATE}}%` | ![98%](https://img.shields.io/badge/98%25-green) |
| **Email Delivery Rate** | ≥ 99% | `{{EMAIL_RATE}}%` | ![99%](https://img.shields.io/badge/99%25-brightgreen) |
| **Forum Engagement** | ≥ 40% weekly active | `{{FORUM_ACTIVE}}%` | ![40%](https://img.shields.io/badge/40%25-yellow) |
| **Timetable Matching Rate** | ≥ 80% find partner | `{{MATCH_RATE}}%` | ![80%](https://img.shields.io/badge/80%25-green) |
| **Page Load Time** | ≤ 2.0s (mobile & desktop) | `{{LCP}}s` | ![1.8s](https://img.shields.io/badge/1.8s-brightgreen) |
| **Material Rating Activity** | ≥ 70% uploads rated | `{{RATING_RATE}}%` | ![72%](https://img.shields.io/badge/72%25-green) |
| **Upload Success Rate** | ≥ 99.5% | `{{UPLOAD_RATE}}%` | ![99.7%](https://img.shields.io/badge/99.7%25-brightgreen) |
| **Accessibility Score** | ≥ 95 (Lighthouse) | `{{A11Y_SCORE}}` | ![96](https://img.shields.io/badge/96-brightgreen) |

> **Live Dashboard**: `https://efs.hku.space/metrics` (Grafana + MongoDB)

---

## 2. DETAILED METRICS & VALIDATION METHODS

### 2.1 Login Success Rate
**Goal**: ≥ 98% of login attempts succeed  
**Validation**:
```js
// Backend log → MongoDB `login_logs` collection
{ userId, success: true/false, timestamp, ip, courseCode }
