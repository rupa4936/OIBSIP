# Task 8 – Capture Network Traffic with Wireshark

## Objective

The objective of this task is to capture and analyze live network traffic using Wireshark. The captured packets were analyzed using HTTP, DNS, and TCP filters. A TCP three-way handshake was also identified and an unencrypted HTTP packet was analyzed.

---

## Tools Used

- Wireshark 4.6.6
- Kali Linux
- Windows XAMPP
- DVWA (Damn Vulnerable Web Application)

---

## Lab Environment

The network traffic was captured in an authorized local lab environment.

### Systems Used

- Kali Linux – Wireshark packet capture
- Windows – XAMPP and DVWA
- Windows DVWA URL:
  `http://192.168.1.102/DVWA/`

The Kali Linux and Windows systems were connected to the same local network.

---

## Wireshark Installation

Wireshark was installed on Kali Linux.

The installed version was verified using:

```bash
wireshark --version# Task 8 – Capture Network Traffic with Wireshark

## Objective

The objective of this task is to capture and analyze live network traffic using Wireshark. The captured packets were analyzed using HTTP, DNS, and TCP filters. A TCP three-way handshake was also identified and an unencrypted HTTP packet was analyzed.

---

## Tools Used

- Wireshark 4.6.6
- Kali Linux
- Windows XAMPP
- DVWA (Damn Vulnerable Web Application)

---

## Lab Environment

The network traffic was captured in an authorized local lab environment.

### Systems Used

- Kali Linux – Wireshark packet capture
- Windows – XAMPP and DVWA
- Windows DVWA URL:
  `http://192.168.1.102/DVWA/`

The Kali Linux and Windows systems were connected to the same local network.

---

## Wireshark Installation

Wireshark was installed on Kali Linux.

The installed version was verified using:

```bash
wireshark --version

Network Interface

The eth0 network interface was selected in Wireshark for capturing network traffic.

A live packet capture was performed for more than two minutes.

Packet Capture

The capture was started on the eth0 interface.

During the capture, the DVWA application running on the Windows system was accessed and refreshed several times to generate HTTP traffic.

After completing the capture, it was stopped and saved as:

wireshark_capture.pcap
HTTP Traffic Analysis

The following Wireshark display filter was used:

http

This filter displays packets related to the HTTP protocol.

The HTTP traffic generated while accessing the DVWA application was analyzed.

Screenshot

http_filter.png

DNS Traffic Analysis

The following display filter was used:

dns

This filter displays DNS packets captured during the network activity.

DNS packets were examined to understand how domain-name resolution traffic appears in Wireshark.

Screenshot

dns_filter.png

TCP Traffic Analysis

The following display filter was initially used:

tcp

TCP packets were then examined to identify the TCP three-way handshake.

The SYN packets were further filtered using:

tcp.flags.syn == 1
TCP Three-Way Handshake

A TCP connection is established using three steps:

SYN – The client sends a SYN packet to request a connection.
SYN-ACK – The server responds with SYN-ACK.
ACK – The client sends an ACK to confirm the connection.

Therefore:

Client                         Server
  |                              |
  | -------- SYN --------------> |
  | <------ SYN + ACK ---------- |
  | -------- ACK --------------> |
  |                              |
       Connection Established
Screenshot

tcp_3way_handshake.png

Unencrypted HTTP Packet

The following filter was used:

http.request

An HTTP request packet generated while accessing DVWA was identified.

HTTP traffic is unencrypted, so information contained in an HTTP request can potentially be viewed by someone who is able to capture the traffic.

For example, an HTTP GET request can reveal information such as:

Requested URL/path
HTTP method
Host information
Headers
Other request metadata
Screenshot

http_unencrypted_packet.png

Why HTTP Is Dangerous

HTTP does not encrypt the communication between the client and server.

Because of this, an attacker who can observe the network traffic may be able to read sensitive information transmitted through HTTP.

Possible risks include:

Eavesdropping
Exposure of sensitive information
Session information leakage
Modification of traffic by attackers

For this reason, sensitive web applications should use HTTPS instead of HTTP.

HTTP vs HTTPS
Feature	HTTP	HTTPS
Encryption	No	Yes
Data protection	Low	Higher
Eavesdropping protection	No	Yes
Common port	80	443
Security	Less secure	More secure

HTTPS uses TLS encryption to protect communication between the client and server.

TCP Three-Way Handshake Summary

The TCP three-way handshake establishes a reliable connection between two systems.

SYN

The client sends a SYN packet to the server.

SYN-ACK

The server acknowledges the request and sends SYN-ACK.

ACK

The client sends an ACK packet to confirm the connection.

After these three steps, TCP communication can proceed.

Important Wireshark Terms
Packet

A packet is a small unit of data transmitted over a network.

Protocol

A protocol is a set of rules used for communication between network devices.

Examples:

TCP
HTTP
DNS
Port

A port is a logical communication endpoint used by network applications.

Examples:

HTTP – Port 80
HTTPS – Port 443
DNS – Port 53
Payload

Payload is the actual data carried inside a network packet.

Handshake

A handshake is a process used by communicating systems to establish or negotiate a connection.

Files Included

The Task 8 folder contains:

Task8-Wireshark/
│
├── README.md
├── wireshark_capture.pcap
├── http_filter.png
├── dns_filter.png
├── tcp_3way_handshake.png
└── http_unencrypted_packet.png
Ethical Considerations

Network packet capture should only be performed on networks and systems that you own or have explicit permission to test.

This task was performed in an authorized local lab environment using a Windows DVWA installation and Kali Linux.

Packet capture should not be performed on public Wi-Fi, university networks, company networks, or other networks without proper authorization.

Conclusion

Wireshark was successfully used to capture and analyze live network traffic.

The task demonstrated:

HTTP packet filtering and analysis.
DNS traffic identification.
TCP three-way handshake analysis using SYN, SYN-ACK, and ACK packets.
Identification of unencrypted HTTP traffic.
The security difference between HTTP and HTTPS.

This exercise demonstrates how packet analysis can help understand network communication and identify potential security risks.

References
Wireshark User Guide
TCP/IP networking documentation
HTTP protocol documentation
OWASP Web Security resources

**Ab next:** is content ko `README.md` mein save karna hai. Uske baad hum folder ko GitHub ke **OIBSIP repo → Task 8 folder** mein upload karenge.
