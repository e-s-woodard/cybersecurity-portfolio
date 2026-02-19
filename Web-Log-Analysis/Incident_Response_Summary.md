# Incident Response Summary
## Web Server Suspicious Activity Investigation

### Incident Overview
On February 18, 2026, suspicious activity was identified within web server access logs. The activity included reconnaissance attempts targeting sensitive application paths and repeated failed authentication attempts followed by a successful login.

### Detection Method
The incident was detected during routine log analysis of web server access logs.

### Timeline of Events
- 21:11:10 – Multiple requests to sensitive paths including `/wp-login.php`, `/wp-admin/`, and `/phpmyadmin/` from IP address 203.0.113.77.
- 21:12:01 – Repeated failed login attempts (`401` responses) to `/login` from IP address 198.51.100.23.
- 21:12:09 – Successful authentication (`200` response) from 198.51.100.23.
- 21:12:30 – Access to `/account` endpoint from the same IP address.

### Impact Assessment
The activity suggests potential automated reconnaissance followed by possible credential compromise. The successful authentication and subsequent access to the account endpoint indicate a risk of unauthorized access.

### Containment & Mitigation Recommendations
- Block or restrict IP addresses 203.0.113.77 and 198.51.100.23.
- Implement rate limiting and account lockout mechanisms.
- Enforce multi-factor authentication (MFA).
- Review account activity for suspicious actions.
- Monitor for continued scanning behavior.

### Lessons Learned
- Web applications should implement stronger authentication protections.
- Monitoring and alerting for repeated failed logins should be automated.
- Sensitive endpoints should be properly secured and monitored.

### Analyst Notes
This investigation was conducted as part of a simulated SOC exercise to demonstrate log analysis and incident documentation skills.
  
