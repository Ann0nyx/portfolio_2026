# 1 - Extended Detection and Response (XDR)
Extended Detection and Response(XDR) is a cybersecurity platform that unifies security telemetry from endpoints,email,cloud workloads,networks and identity systems into a single solution. It builds on Endpoint Detection and Responce(EDR) by extending visiblity across the entire environment and applies behavioural analytics, machine learning and threat correlation to detect attacks signature based tools typically miss. XDR also automates response actions such as isolating infected hosts or disabling compromised accounts to contain threats quickly.

## Why is it considered State of art?
Modern attackers move across email, accounts, endpoints, cloud, and networks during multi-stage attacks, creating visibility gaps in siloed tools. XDR is state-of-the-art because it provides unified visibility, correlates signals across domains, uses machine learning for real-time detection, reduces false positives, and automates investigation and response — enabling faster identification of advanced threats.

## Evidence
IBM describes XDR as unifying endpoints, networks, cloud, applications, email, and identities under one architecture, using advanced analytics and machine learning for real-time threat detection. CrowdStrike's Falcon Insight XDR similarly centralises telemetry to improve investigation, threat hunting, and response. 

# 2 - Zero trust Architecture
Zero Trust Architecture (ZTA) is based on the principle "never trust, always verify." Rather than assuming internal users and devices are trustworthy, it continuously validates every user, device, application, and access request. Key controls include MFA, least-privilege access, device verification, micro-segmentation, and continuous authentication, all aimed at reducing unauthorised access and lateral movement.

## Why is it considered State of art?
Traditional perimeter-based security assumes internal trust, but attackers routinely bypass perimeters through phishing, credential theft, and insider threats. Zero Trust is state-of-the-art because it continuously verifies identities and devices, minimises permissions, limits lateral movement, and securely supports cloud, hybrid, and remote-work environments.

## Evidence
NIST SP 800-207 defines Zero Trust as a model that minimises uncertainty and enforces least-privilege access through continuous verification of users, devices, applications, and transactions. 

# 3 - cloud-Native Security
Cloud-native security is designed specifically to protect cloud environments, workloads, containers, Kubernetes clusters, APIs, and cloud applications. It includes Cloud Security Posture Management (CSPM), Cloud Workload Protection Platforms (CWPP), Kubernetes security, runtime threat detection, Infrastructure-as-Code scanning, and cloud identity monitoring. These tools continuously monitor for misconfigurations, exposed services, insecure APIs, vulnerable containers, and abnormal runtime behaviour.

## Why is it considered State of art?
Organisations increasingly rely on AWS, Azure,Google Cloud and Kubernetes while attackers target cloud misconfigurations, exposed APIs, and stolen credentials. Cloud-native security is state-of-the-art because it provides multicloud visibility, supports dynamic infrastructure, uses runtime behavioural monitoring, and automates vulnerability and exposure management.

## Evidence
A Forrester Total Economic Impact™ study cited in CrowdStrike material reported that Falcon Cloud Security delivered a 20–30% improvement in mean time to detect, around 30% improvement in mean time to respond, and 45% better cloud security visibility.
