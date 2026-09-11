# Common Network Security Threats

## Introduction

Network security threats are attacks or activities that can harm computer networks, systems, or users. These threats may affect the availability, confidentiality, and integrity of network resources.

This report discusses common network security threats, including DoS/DDoS, Man-in-the-Middle (MITM), IP Spoofing, and DNS Poisoning/Spoofing. It explains their impact and the methods that can be used to reduce their risks.

## 1. DoS / DDoS Attack

### What is DoS/DDoS?

Denial of Service (DoS) is an attack that attempts to make a network service or system unavailable to legitimate users. Distributed Denial of Service (DDoS) is a similar attack in which traffic or requests come from multiple sources.

### Real-World Example

A DDoS attack can target a website or online service by generating a very large amount of traffic. If the service cannot handle the traffic, legitimate users may experience slow performance or become unable to access the service.

### Impact

DoS/DDoS attacks can cause:

- Website or service unavailability
- Slow network performance
- Loss of productivity
- Financial losses
- Damage to an organization's reputation

### Mitigation Methods

1. Use firewalls and network security controls to filter suspicious traffic.
2. Use DDoS protection and traffic-monitoring services.
3. Monitor network traffic and establish alerts for unusual traffic patterns.

## 2. Man-in-the-Middle (MITM) Attack

### What is MITM?

A Man-in-the-Middle (MITM) attack occurs when an attacker gets between two parties communicating with each other and attempts to intercept or manipulate their communication.

For example, communication between a user and a website can be intercepted if the connection is not properly protected.

### Real-World Example

An attacker on an unsecured or compromised network may attempt to intercept communication between a user and an online service. This can expose information being transmitted over the connection.

### Impact

MITM attacks can result in:

- Unauthorized interception of communication
- Exposure of sensitive information
- Modification of transmitted data
- Account or session compromise
- Loss of confidentiality

### Mitigation Methods

1. Use HTTPS and other encrypted communication protocols.
2. Avoid connecting to unknown or untrusted networks.
3. Use strong authentication and secure network configurations.

## 3. IP Spoofing

### What is IP Spoofing?

IP spoofing is a technique in which an attacker changes or falsifies the source IP address of network packets. This can make the traffic appear to come from a different source.

### Real-World Example

An attacker may use a spoofed source IP address when sending malicious network traffic. The receiving system may initially see the forged address instead of the attacker's actual address.

### Impact

IP spoofing can contribute to:

- Hiding the true source of network traffic
- Network-based attacks
- Unauthorized access attempts
- Difficulty in tracing malicious traffic
- Disruption of network services

### Mitigation Methods

1. Use ingress and egress filtering to detect and block packets with invalid source addresses.
2. Monitor network traffic for unusual or suspicious source IP addresses.
3. Use secure authentication methods instead of trusting an IP address alone.

## 4. DNS Poisoning / Spoofing

### What is DNS Poisoning?

DNS poisoning, also called DNS spoofing in some contexts, is an attack in which false DNS information is provided or stored so that users can be directed to an incorrect destination.

DNS normally translates a domain name into an IP address. If this information is manipulated, a user may be redirected to a malicious or unintended destination.

### Real-World Example

An attacker may attempt to manipulate DNS information so that a legitimate domain name resolves to an attacker-controlled IP address. Users may then be directed to a fraudulent website.

### Impact

DNS poisoning can result in:

- Users being redirected to malicious websites
- Exposure of sensitive information
- Phishing attacks
- Loss of trust in network services
- Interruption of legitimate services

### Mitigation Methods

1. Use DNS security mechanisms and properly configured DNS servers.
2. Keep DNS server software updated and securely configured.
3. Monitor DNS traffic and investigate unusual DNS responses or changes.

## 5. Comparison of Network Security Threats

| Attack Type              | Attack Vector                               | At-Risk Party                | Difficulty | Ease of Mitigation |
| ------------------------ | ------------------------------------------- | ---------------------------- | ---------- | ------------------ |
| DoS / DDoS               | Large volume of network traffic or requests | Servers and online services  | Medium     | Medium             |
| MITM                     | Interception of network communication       | Users and transmitted data   | Medium     | Medium             |
| IP Spoofing              | Forged source IP addresses                  | Network systems and services | Medium     | Medium             |
| DNS Poisoning / Spoofing | Manipulation of DNS information             | Users and network services   | Medium     | Medium             |


## 6. Conclusion

Network security threats can affect the availability, confidentiality, and integrity of network resources. DoS/DDoS attacks can disrupt services, MITM attacks can expose communication, IP spoofing can hide the true source of traffic, and DNS poisoning can redirect users to unintended destinations.

### 3 Key Takeaways for Network Administrators

1. Regularly monitor network traffic and investigate unusual activity.
2. Use secure protocols, strong authentication, firewalls, and properly configured network security controls.
3. Keep network and DNS systems updated, securely configured, and regularly reviewed.

## 7. References

1. National Institute of Standards and Technology (NIST) — Cybersecurity resources and guidance.
2. Cybersecurity and Infrastructure Security Agency (CISA) — Cybersecurity guidance and best practices.
3. MITRE ATT&CK — Enterprise attack techniques and security knowledge base.
4. SANS Institute — Information security resources and training materials.