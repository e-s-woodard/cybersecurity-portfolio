## Project Overview
This project simulates a real-world SOC scenario where SSH authentication logs are reviewed to detect suspicious login behavior and potential brute-force attacks.

# SSH Log Analysis Project

## Objective
Analyze SSH server logs to identify suspicious login behavior and potential brute-force attacks.

## Dataset
Sample SSH log file (manually created for analysis practice).

## Observations
- IP address 192.168.1.50 generated 5 failed login attempts within seconds.
- The attempts targeted common usernames such as "admin" and "root."
- A successful login was recorded shortly after the failed attempts.
- A second IP address (198.51.100.27) also generated multiple failed login attempts minutes later.

## Analysis
The rapid succession of failed login attempts from 192.168.1.50 suggests a potential brute-force attack, as humans typically cannot attempt multiple passwords within seconds.

The presence of a successful login event raises concern and should be investigated to determine whether it was legitimate or unauthorized.

The repeated failed attempts from a second IP address indicate additional suspicious activity that may represent automated attack behavior.

## Recommendations
- Block or monitor IP addresses 192.168.1.50 and 198.51.100.27.
- Implement account lockout policies after a certain number of failed login attempts.
- Enable multi-factor authentication (MFA).
- Continuously monitor logs for repeated patterns of failed authentication attempts.

## Skills Demonstrated
- Log analysis
- Pattern recognition
- Threat detection
- Security documentation
- Incident reporting
