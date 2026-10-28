# Networking and Internet Security

## 1. What Is Computer Networking?

A computer network connects devices so they can exchange information and share resources.

Examples include home Wi-Fi, school networks, company networks, and the internet.

## 2. Network Components

- Router: Forwards traffic between networks.
- Switch: Connects devices within a local network.
- Access point: Provides wireless network access.
- Firewall: Filters network traffic using rules.
- Client: Requests a service.
- Server: Provides a service.
- DNS resolver: Helps translate domain names into DNS records.

## 3. IP Addresses

An IP address identifies a network interface for communication.

### IPv4
Uses 32-bit addresses, commonly written as four decimal numbers, such as `192.168.1.10`.

### IPv6
Uses 128-bit addresses and supports a much larger address space.

Private IP addresses are commonly used inside local networks. A public IP address is used for communication across the public internet, subject to network configuration.

## 4. Ports and Protocols

A port helps a computer direct network traffic to an application or service.

Common default ports include:

- 22: SSH.
- 25: SMTP.
- 53: DNS.
- 80: HTTP.
- 123: NTP.
- 443: HTTPS.
- 445: SMB.
- 587: Email message submission.
- 3389: Commonly used by Remote Desktop Protocol.

These are typical assignments, not proof that a particular service is running.

## 5. TCP and UDP

### TCP
TCP provides a connection-oriented byte stream with mechanisms for reliable, ordered delivery.

### UDP
UDP sends datagrams without TCP's built-in delivery and ordering guarantees.

Applications choose a transport protocol according to their requirements.

## 6. DNS

The Domain Name System helps resolve domain names into records such as IP addresses.

Security risks include malicious domains, unauthorized DNS changes, spoofing, and unsafe resolver configurations.

Defensive practices include using trusted resolvers, securing domain registrar accounts, monitoring DNS changes, and protecting administrative access.

## 7. HTTP and HTTPS

HTTP is used to transfer web requests and responses.

HTTPS protects HTTP traffic using TLS. Properly configured TLS helps provide encryption in transit, data integrity, and server authentication.

Important: HTTPS does not prove that a website is legitimate. Phishing websites can also use HTTPS.

## 8. Firewalls

A firewall allows or blocks traffic according to configured rules.

Rules may consider source addresses, destination addresses, ports, protocols, and connection state.

Good practices include:
- Block unnecessary traffic.
- Restrict administrative access.
- Document exceptions.
- Review rules periodically.
- Monitor relevant firewall logs.

## 9. VPNs

A Virtual Private Network creates a protected tunnel between endpoints or networks.

VPNs can protect traffic across untrusted networks, but they do not eliminate malware, phishing, unsafe downloads, or every privacy risk.

## 10. Wi-Fi Security

- Use WPA3 or WPA2-AES when supported.
- Set a long, unique Wi-Fi passphrase.
- Change default router administrator credentials.
- Update router firmware.
- Disable unnecessary remote administration.
- Use guest Wi-Fi for visitors.
- Review connected devices.
- Avoid obsolete wireless security protocols.

## 11. Network Monitoring

Defenders examine network and system logs to detect suspicious activity.

Useful sources include DNS logs, firewall events, authentication records, network flow data, and endpoint alerts.

Logs should have reliable timestamps, restricted access, and suitable retention.

## 12. Safe Practice Exercises

On your own computer or an explicitly authorized lab:

1. Find your local IP address using network settings.
2. Identify your default gateway.
3. Explain the difference between a router and a switch.
4. Visit a trusted website and identify whether it uses HTTPS.
5. Draw a diagram showing a client, router, DNS resolver, and web server.

Never scan or probe a network without authorization.

## 13. Review Questions

1. What is an IP address?
2. What is a port?
3. How do TCP and UDP differ?
4. What does DNS do?
5. Why is HTTPS not proof that a website is trustworthy?
6. What is the purpose of a firewall?
7. What security benefits and limitations does a VPN have?

## 14. Answers

1. It identifies a network interface for communication.
2. It helps deliver network traffic to an application or service.
3. TCP provides ordered delivery mechanisms; UDP does not provide the same built-in guarantees.
4. DNS resolves domain names into records, including IP addresses.
5. Malicious websites can also use HTTPS.
6. A firewall filters traffic according to security rules.
7. A VPN protects traffic through a tunnel, but does not eliminate endpoint threats or guarantee anonymity.
