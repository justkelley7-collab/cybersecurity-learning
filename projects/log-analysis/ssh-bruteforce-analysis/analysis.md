## Analysis

Multiple failed SSH login attempts were observed from a single IP
address targeting several usernames in a short time frame.

### Findings
- Attacker IP: 192.168.56.101
- Attack type: SSH brute-force / credential guessing
- Usernames targeted: admin, root, test, john
- Successful authentication occurred for user "john"

### Timeline
- 10:15:21–10:15:30: Repeated failed login attempts
- 10:15:45: Successful login
- 10:16:01: Session opened

### Assessment
The log activity strongly indicates a successful brute-force attack.
Post-compromise activity cannot be confirmed from authentication logs alone.

### Recommendations
- Disable password-based SSH authentication
- Enforce key-based authentication
- Implement rate limiting or fail2ban
- Review post-login activity logs
