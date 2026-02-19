# Web Server Access Log Analysis Project

## Objective
Analyze web server access logs to identify suspicious activity such as scanning and potential brute-force/credential stuffing attempts.

## Dataset
Sample web server access log file: `access_log_sample.txt` (created for analysis practice).

## Key Findings

### 1) Reconnaissance / Scanning Activity
- **Source IP:** 203.0.113.77
- Multiple requests were made to commonly targeted sensitive paths:
  - /wp-login.php
  - /wp-admin/
  - /phpmyadmin/
- These paths are frequently targeted by automated scanners searching for exposed admin panels or vulnerable services.
- The rapid sequence of requests suggests automated reconnaissance activity.

### 2) Suspicious Authentication Pattern
- **Source IP:** 198.51.100.23
- Observed four consecutive failed login attempts (`401` responses) to `/login`.
- A subsequent login attempt returned a `200` (successful authentication).
- Immediately after the successful login, a `GET /account` request was made.

### Interpretation
The repeated failed login attempts followed by a successful authentication may indicate a successful brute-force or credential stuffing attack. The access to `/account` after login suggests the actor may have gained unauthorized access to the account.
