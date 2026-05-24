# B2 - Discover 5 unique Strong security implementations
## Identified Strong Security Implementations are - 
### 1) DMARC Email Authentication
#### Website tested: 
Google
#### Command used - 
dig TXT _dmarc.google.com

#### Evidence Found –  
v=DMARC1; p=reject; rua=mailto:mailauth-reports@google.comStrong

#### Security Implementation Identified -
Google has implemented Domain-based Message Authentication, Reporting and Conformance (DMARC) with a policy set to “reject.” DMARC works alongside SPF and DKIM to verify whether incoming emails claiming to originate from the domain are legitimate.
#### Security Benefit -
A reject policy means spoofed emails that fail authentication checks are blocked entirely by receiving mail servers instead of being delivered to inboxes. This significantly reduces phishing attacks, email impersonation, and business email compromise attempts targeting users of the domain. This implementation focuses on email infrastructure security rather than website or browser protection mechanisms.


### 2) HTTPS Enforcement and Secure Redirection
#### Website tested: 
Google
#### Command used - 
curl -I https://google.com 

#### Evidence found - 
HTTP/2 301 
location: https://www.google.com/ 
#### Strong Security Implementation Identified -
Google enforces encrypted HTTPS communication and automatically redirects users from insecure HTTP requests to secure HTTPS connections. HTTPS uses TLS (Transport Layer Security) to encrypt data transmitted between users and the server.
#### Security Benefit - 
TLS encryption protects sensitive information such as passwords, session cookies, and search data from interception during transmission. It also helps defend against man-in-the-middle (MITM) attacks where attackers attempt to alter or monitor network traffic. This implementation focuses on network and transport-layer encryption security, which differs from browser-side protections or email authentication.
### 3) Content Security Policy (CSP)
#### Website tested - 
Stripe
#### Command used - 
curl -I https://stripe.com

#### Evidence found - 
content-security-policy

#### Strong Security Implementation Identified -
Stripe implements a Content Security Policy (CSP) which controls which scripts, resources and external content are allowed to execute within the browser when visiting the website.
#### Security Benefit -
CSP reduces the likelihood of Cross-Site Scripting (XSS) attacks by preventing malicious scripts from running if they originate from unapproved sources. This helps protect user sessions, payment information and sensitive browser interactions from client side exploitation. This implementation focuses on browser side script execution control and web application security.

### 4) HTTP Strict Transport Security (HSTS)

#### Website tested – 
GitHub
#### Command used - curl -I https://github.com 

#### Evidence found - 
strict-transport-security: max-age=31536000; includeSubdomains ; preload
#### Strong Security Implementation Identified -
GitHub uses HTTP Strict Transport Security (HSTS), which instructs browsers to only communicate with the website using HTTPS connections for a specified period of time.
#### Security Benefit -
HSTS prevents downgrade and SSL stripping attacks where attackers attempt to force users onto insecure HTTP connections. Even if a user manually types “http://”, the browser will automatically convert the request to HTTPS before connecting. This implementation focuses specifically on HTTPS enforcement and downgrade attack prevention, rather than general encryption or script protection.

### 5) Clickjacking Protection Using X-Frame-Options
#### Website tested: 
Github
#### Command used - 
curl -I https://github.com 

#### Evidence found - 
x-frame-options: deny
#### Strong Security Implementation Identified -
GitHub prevents its webpages from being embedded within frames or iframes on external websites using the X-Frame-Options: deny header.
#### Security Benefit -
This protects against clickjacking attacks, where attackers overlay invisible website elements inside malicious pages to trick users into performing unintended actions such as clicking buttons, authorising requests or revealing sensitive information. This implementation focuses on user interface and browser interaction security which differs from transport encryption, email authentication or script execution protections.

