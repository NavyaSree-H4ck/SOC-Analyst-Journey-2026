[TCP_IP_Model.md](https://github.com/user-attachments/files/29247552/TCP_IP_Model.md)
                                           2.TCP/IP Model 
Overview
The TCP/IP (Transmission Control Protocol/Internet Protocol) model is the standard framework used for communication over the Internet and modern networks. It defines how data is packaged, transmitted, routed, and received between devices.
Layers of the TCP/IP Model
1. Application Layer
Purpose: Provides network services directly to user applications.
Functions:
Enables communication between applications and the network.
Supports web browsing, email, file transfer, and remote access.
Protocols:
HTTP/HTTPS
FTP
SMTP
DNS
SSH
DHCP
Examples:
Accessing websites
Sending emails
Remote login using SSH
2. Transport Layer
Purpose: Ensures reliable and efficient data transfer between devices.
Functions:
Segmentation and reassembly of data
Error detection and recovery
Flow control and port addressing
Protocols:
TCP (Transmission Control Protocol)
UDP (User Datagram Protocol)
Examples:
Web browsing (TCP)
Video streaming and online gaming (UDP)
3. Internet Layer
Purpose: Handles logical addressing and routing of packets across networks.
Functions:
Assigns IP addresses
Routes packets to destination networks
Performs packet fragmentation
Protocols:
IP (IPv4/IPv6)
ICMP
ARP
IGMP
Examples:
Routing data across the Internet
Ping operations using ICMP
4. Network Access Layer (Link Layer)
Purpose: Manages communication between devices on the same physical network.
Functions:
Frame creation
MAC addressing
Physical transmission of data
Protocols/Technologies:
Ethernet
Wi-Fi (IEEE 802.11)
PPP
Frame Relay
Examples:
Data transfer over LAN
Wireless communication
Encapsulation Process
Application Layer   → Data
Transport Layer     → Segment
Internet Layer      → Packet
Network Access Layer→ Frame
Physical Medium     → Bits
Significance of the TCP/IP Model
Standard Communication Framework: Enables interoperability between different devices and operating systems.
Scalability: Supports networks ranging from small LANs to the global Internet.
Reliability: TCP provides error checking, retransmission, and flow control.
Efficient Routing: IP allows packets to travel through multiple interconnected networks.
Protocol Independence: Supports various applications and network technologies.
Foundation of the Internet: Forms the basis of modern Internet communication.

Practical Example
When a user opens https://www.google.com:
Application Layer creates an HTTPS request.
Transport Layer (TCP) establishes a connection and divides data into segments.
Internet Layer (IP) assigns source and destination IP addresses and routes packets.
Network Access Layer converts packets into frames and transmits them over Ethernet or Wi-Fi.
The destination host processes the data in reverse order and sends a response.

Conclusion
The TCP/IP model is the foundation of modern networking. Its four-layer architecture enables reliable communication, efficient routing, and interoperability between devices, making global Internet connectivity possible.

Layer Mapping Table

PDU (Protocol Data Unit)

Devices Involved



