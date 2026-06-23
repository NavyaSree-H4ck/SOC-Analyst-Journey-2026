                                              
                                               1.OSI Model

1.1 What is the OSI Model?
The Open Systems Interconnection (OSI) Model is a framework developed by the International Organization for Standardization (ISO) that describes how data moves from one device to another over a network.
When two devices communicate, many things happen:
Applications generate data. 
Data is formatted and encrypted. 
Connections are established. 
Data is divided into smaller pieces. 
IP addresses are assigned. 
MAC addresses are used. 
Electrical signals or wireless waves carry the information. 

1.2 Why is the OSI Model Important?

a) Standardization
The OSI model provides a standard framework for network communication. It ensures that devices and software from different vendors can communicate with each other using common protocols.
Example: A Windows PC can communicate with a Linux server through a Cisco router.

b) Modularity
The communication process is divided into seven layers, and each layer performs a specific task independently. Changes or problems in one layer usually do not affect other layers.
Example: An application can be updated without changing the routing process.

c) Easier Troubleshooting
Since networking is divided into layers, problems can be isolated to a specific layer, making troubleshooting easier.
Examples:
Layer 1 → Cable issue
Layer 2 → MAC address or switch issue
Layer 3 → IP address or routing problem
Layer 4 → Port blocked
Layer 7 → Application failure

d) Protocol Development
Protocols are designed for specific layers and perform dedicated functions.
Examples:
HTTP/HTTPS → Application Layer
TCP/UDP → Transport Layer
IP → Network Layer
Ethernet → Data Link Layer
This separation allows new protocols to be developed without affecting other layers.

e) Interoperability
Devices and software from different manufacturers can work together because they follow standard protocols.
Example:
Client (Windows) → Cisco Router → ISP Router → Linux Server
Even though different vendors are involved, communication is possible because they use common protocols such as TCP/IP and Ethernet.

f) Simplifies Maintenance
Problems or upgrades in one layer can often be handled without affecting the entire network.
Example: Replacing an Ethernet cable (Layer 1) does not require changes to HTTP or TCP.

g) Provides Flexibility
New technologies and protocols can be introduced without redesigning the whole network architecture.
Example: IPv6 was introduced at Layer 3 while higher-layer protocols like HTTP and HTTPS remained unchanged.
h) Helps Understand Data Flow
The OSI model explains how data travels from sender to receiver through different layers


Sender Side: Encapsulation 
Suppose you type: https://www.google.com on your browser.
Your computer must:
Generate an HTTPS request.
Encrypt the message.
Establish a communication session.
Divide the message into segments.
Add source and destination IP addresses.
Add source and destination MAC addresses.
Convert everything into binary bits.
Send the bits through Wi-Fi or Ethernet and data reaches the google server.

Receiver Side: Decapsulation

The request has already travelled across the Internet and arrived at Google's server.
Now Google's server must:
Receive the binary bits through its Ethernet cable or Wi-Fi. 
Convert the bits back into frames. 
Read the source and destination MAC addresses. 
Remove the Data Link header and trailer. 
Read the source and destination IP addresses. 
Remove the IP header. 
Reassemble the TCP segments in the correct order. 
Verify that no segments are missing. 
Maintain the communication session. 
Decrypt the HTTPS message using TLS. 
Process the HTTP request. 
Generate the webpage response.

1.3 PDU (Protocol Data Unit)
A PDU (Protocol Data Unit) is the form in which data exists at a particular layer of the OSI model. 
Example
Suppose you type: https://www.google.com
The browser creates an HTTP request:
GET / HTTP/1.1
Host: www.google.com

At the Application Layer, this request is called Data. As it moves down the OSI layers, headers are added and the PDU changes:

1.4 Layer 7 – Application Layer
Overview
The Application Layer is the top layer of the OSI model. It provides network services directly to user applications and acts as the interface between the user and the network. It enables services such as web browsing, email, file transfer, and remote access.
Functions
Provides network access to applications. 
Supports communication between client and server. 
Handles resource sharing and user authentication. 
Enables services like web browsing, email, and file transfer. 
Common Protocols and Use Cases
HTTP (Port 80)
Purpose: Transfers web pages and web content.
Use Case: Browsing websites.

HTTPS (Port 443)
Purpose: Provides secure web communication using TLS encryption.
Use Case: Online banking, Gmail, shopping websites.

FTP (Ports 20, 21)
Purpose: Transfers files between systems.
Use Case: Uploading and downloading files from servers.

TFTP (Port 69 UDP)
Purpose: Provides simple file transfer without authentication.
Use Case: Firmware updates and network device configuration backups.

SMTP (Ports 25, 587, 465)
Purpose: Sends outgoing email messages.
Use Case: Sending emails from Gmail, Outlook, and mail servers.

POP3 (Ports 110, 995)
Purpose: Downloads emails from the mail server.
Use Case: Accessing emails offline.

IMAP (Ports 143, 993)
Purpose: Synchronizes emails between the server and multiple devices.
Use Case: Accessing the same mailbox from laptops and smartphones.

DNS (Port 53 TCP/UDP)
Purpose: Resolves domain names into IP addresses.
Use Case: Converting www.google.com into an IP address.

DHCP (Ports 67, 68)
Purpose: Automatically assigns IP addresses and network settings.
Use Case: Connecting devices to a network without manual configuration.

SSH (Port 22)
Purpose: Provides secure remote access to systems.
Use Case: Managing Linux servers and network devices.

Telnet (Port 23)
Purpose: Provides remote access without encryption.
Use Case: Legacy device administration.

SNMP (Ports 161, 162)
Purpose: Monitors and manages network devices.
Use Case: Monitoring routers, switches, firewalls, and servers.

NTP (Port 123 UDP)
Purpose: Synchronizes time across network devices.
Use Case: Maintaining accurate timestamps for logs and servers.

LDAP (Ports 389, 636)
Purpose: Provides centralized directory and authentication services.
Use Case: Microsoft Active Directory environments.

1.5 Layer 6 – Presentation Layer
Overview
The Presentation Layer (Layer 6) is responsible for formatting, translating, encrypting, and compressing data so that it can be understood by the receiving device. It acts as a translator between the Application Layer and the lower layers.
Functions
Data Translation
Converts data into a format understood by both sender and receiver.
Example:
ASCII ↔ Unicode
JPEG ↔ Bitmap
Encryption and Decryption
Secures data before transmission and decrypts it at the receiver.
Protocols:
SSL
TLS
Example:
HTTPS uses TLS encryption.
Compression and Decompression
Reduces the size of data to improve transmission efficiency.
Examples:
JPEG
PNG
GIF
MP3
MPEG
Use Case
When you open:
https://www.google.com
The Presentation Layer encrypts the HTTP data using TLS before it is transmitted and decrypts it when it reaches the destination.
1.6 Session Layer (Layer 5)
Overview
The Session Layer establishes, manages, and terminates communication sessions between two devices. It ensures that communication remains active and synchronized throughout the data exchange.
Functions
Establishes communication sessions.
Maintains and synchronizes active sessions.
Terminates sessions after communication is complete.
Provides checkpoints for recovery if a connection is interrupted.
Protocols
NetBIOS
RPC (Remote Procedure Call)
SIP (Session Initiation Protocol)
PPTP (Point-to-Point Tunnelling Protocol)
Use Cases
Video conferencing (Zoom, Teams)
Voice calls (VoIP)
Remote procedure calls
Maintaining user login sessions
Example
When you join a Zoom meeting:
The session starts when you connect.
The session remains active during the meeting.
If the network temporarily fails, synchronization helps resume communication.
The session ends when you leave the meeting.
1.7 Layer 4 – Transport Layer
Overview
The Transport Layer is responsible for end-to-end communication between devices. It ensures that data is delivered correctly, reliably, and in the proper order.
Functions
Segments large data into smaller pieces.
Provides reliable data delivery.
Performs error detection and recovery.
Controls the flow of data.
Uses port numbers to identify applications.
Protocols Used
TCP (Transmission Control Protocol)
Connection-oriented and reliable.
Uses acknowledgments and retransmissions.
Ensures data arrives in order.
Use Cases:
HTTP/HTTPS
FTP
SSH
Email services
UDP (User Datagram Protocol)
Connectionless and faster.
No acknowledgments or retransmissions.
Suitable for real-time communication.
Use Cases:
DNS
VoIP
Online gaming
Video streaming
Common Ports
HTTP – 80
HTTPS – 443
FTP – 21
SSH – 22
DNS – 53
Example
When you access a website, the Transport Layer breaks the data into segments, assigns source and destination port numbers, and delivers the segments to the correct application on the receiving device.
1.8 Layer 3 – Network Layer
Purpose
Responsible for delivering packets from one network to another using logical addressing (IP addresses).
Functions
Provides logical addressing (IPv4/IPv6).
Determines the best path for data using routing.
Forwards packets between different networks.
Performs packet fragmentation if required.
Protocols
IPv4
IPv6
ICMP
IPsec
OSPF
RIP
BGP
Devices
Router
Layer 3 Switch
Firewall
Example
Suppose a laptop with IP address 192.168.1.10 wants to access Google's server 142.250.196.14.
The Network Layer adds the source and destination IP addresses and routers determine the best path to deliver the packet to the destination.
Use Cases
Internet communication
Routing between networks
Connecting LANs and WANs
Packet forwarding across the Internet
1.9 Layer 2 – Data Link Layer
The Data Link Layer is responsible for communication between devices on the same network. It receives packets from the Network Layer and converts them into frames for transmission.
Functions
Provides node-to-node communication.
Uses MAC addresses for device identification.
Performs framing of data.
Detects errors using FCS (Frame Check Sequence).
Controls access to the physical medium.
Protocols
Ethernet (IEEE 802.3)
ARP
PPP
VLAN (802.1Q)
STP (Spanning Tree Protocol)
Devices Used
Switch
Bridge
Network Interface Card (NIC)
Address Used
MAC Address
Example:
00:1A:2B:3C:4D:5E
Use Case
When a computer sends data to another device within the same LAN, the Data Link Layer uses MAC addresses to deliver frames to the correct device through a switch.
Example:
Laptop → Switch → Printer
The switch forwards frames based on MAC addresses, enabling communication within the local network.

1.10 Layer 1 – Physical Layer
Overview
The Physical Layer is the lowest layer of the OSI model. It is responsible for transmitting raw bits (0s and 1s) between devices through physical media such as cables, fiber optics, or wireless signals.
Functions
Converts data into binary bits.
Transmits and receives electrical, optical, or radio signals.
Defines cables, connectors, voltage levels, and transmission speeds.
Provides the physical connection between devices.

Devices Used
Hub
Repeater
Cables (Ethernet, Fiber Optic)
Connectors (RJ-45)
Wireless Access Point (signal transmission)
Standards and Technologies
Ethernet (IEEE 802.3)
Wi-Fi (IEEE 802.11)
Bluetooth
DSL
USB
Fiber Optics
Use Cases
Sending data through Ethernet cables.
Wireless communication using Wi-Fi.
Fiber-optic communication in ISPs.
Connecting computers to switches and routers.
Example
When you open:
https://www.google.com
At the Physical Layer, the frame is converted into:
101010110010101001...
These bits are transmitted as:
Electrical signals (Ethernet cable)
Light pulses (Fiber optics)
Radio waves (Wi-Fi)
The receiving device converts these signals back into bits and passes them to the Data Link Layer.
