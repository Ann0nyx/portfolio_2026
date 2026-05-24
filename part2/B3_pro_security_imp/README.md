# B3 - Discover 3 proactive security implementation in practice

## 1) Cloudflare DDoS Protection and Traffic Filtering

A proactive security implementation was identified as seen in the evidence through Cloudflare reverse proxy protection used by Discord. Cloudflare provides traffic filtering, caching, and Distributed Denial of Service (DDoS) mitigation services to websites and online platforms.

### Command used
```bash
curl -I https://discord.com
```

### Which revealed
```text
server: cloudflare
cf-ray:
cf-cache-status:
```

This indicates that incoming traffic is routed through Cloudflare infrastructure before reaching the origin server.

### Why it is Proactive

This implementation proactively blocks malicious traffic before it reaches the target infrastructure. Suspicious requests, automated bots, and DDoS traffic are filtered at the network edge to reduce the likelihood of service disruption or compromise.

### Analysis

Cloudflare acts as a protective intermediary between users and backend infrastructure. By absorbing and filtering malicious traffic before it reaches the server, the implementation significantly improves service availability and resilience against large-scale attacks.

---

## 2) Multi-Factor Authentication (MFA) and Passkey Authentication

### Description

A proactive authentication security implementation was observed on GitHub through Multi-Factor Authentication (MFA) and passkey authentication mechanisms.

### Explanation

GitHub account security settings showed Two-factor authentication enabled, Two-factor authentication enabled, Passkey authentication configured and Multiple secure sign-in methods available.The implementation requires additional authentication factors beyond a password.

### Why it is Proactive?

This implementation proactively prevents unauthorised access even if passwords are stolen through phishing, credential stuffing, or password reuse attacks.

### Analysis

Traditional password-only authentication creates a single point of failure. MFA and passkey authentication reduce this risk by requiring additional cryptographic or device-based verification before account access is granted.

---

## 3) Chrome Browser Sandboxing and Process Isolation

### Description

A proactive browser security implementation was identified in Google Chrome through process isolation and sandboxing architecture.

### Explanation

Chrome Task Manager demonstrated separate tab processes, isolated extension processes and independent renderer processes. This indicates browser compartmentalisation and sandbox enforcement.

### Why it is Proactive?

The sandbox restricts malicious webpages or exploited browser processes from accessing sensitive system resources or other browser tabs.

### Analysis

Browser sandboxing reduces the impact of client-side attacks by isolating processes into restricted environments. Even if malicious code executes inside one tab, the sandbox limits its ability to compromise the operating system or spread across the browser environment.
