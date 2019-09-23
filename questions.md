# Question 1

A host receives a frame and discards it because it is corrupt, at which layer in the OSI 7-Layer model are frames checked for errors?

 - [ ] Application
 - [ ] Presentation
 - [ ] Session
 - [ ] Transport
 - [ ] Network
 - [x] Data-link
 - [ ] Physical

# Question 2

What are the two types of IP address available for internet communication:

 - [ ] IPv1 (10-bit) and IPv4 (32-bit)
 - [x] IPv4 (32-bit) and IPv6 (128-bit)
 - [ ] IPv4 (24-bit) and IPvNEXT (1024-bit)
 - [ ] IPv4 (24-bit) and IPv6 (32-bit)

# Question 3

Select _all of the options_ below that are true of the OSI 7-Layer model:

 - [ ] The 7-Layer model is maintained by the International Standards Organisation.
 - [ ] All internet protocol stacks must comply with the 7-Layer model.
 - [x] The 7-Layer model includes abstraction between different network, enabling traffic to be carried across multiple types of interconnects.
 - [x] The protocol that governs most of the internet, TCP/IP was not defined under the 7-Layer model.

# Questions 4

What is the primary function of the transport layer:

 - [x] Reliable transmission of data frames between two nodes.
 - [ ] Routing of traffic across a network.
 - [ ] Encryption of traffic across the network.
 - [ ] None of the above

# Question 5

What is the correct CIDR representation of the network 192.168.254.0 with mask 255.255.255.0:

 - [ ] Class C
 - [ ] 192.168.254.1/16
 - [x] 192.168.254.0/24
 - [ ] 255.255.255.0/32

# Question 6

What is a VPN:

 - [ ] Visual Protocol Name
 - [ ] Variable Power Network
 - [ ] Virtual Private Cloud
 - [x] Virtual Private Network

# Question 7

Select the correct definition of an AnyCast IP address:

 - [x] AnyCast IP addresses are typically hosted in multiple locations any of which are capble of responding to clients equally.
 - [ ] AnyCast IP addresses broadcast traffic to any listening address.
 - [ ] AnyCast IP addresses deal exclusively with free-to-air TV broadcasts.
 - [ ] None of the Above

# Question 8

A Layer-7 Firewall is capabile of blocking which types of threats:

 - [ ] Direct attacks to the DNS system.
 - [x] Attacks against an application protocol such as HTTP.
 - [ ] Attacks leveled against a backend DHCP service.
 - [ ] Only attacks that are against unencrypted traffic, i.e. HTTP only.

# Question 9

How many IP address are available in a /16 CIDR subnet:

 - [x] 65,536
 - [ ] 16
 - [ ] 64,000
 - [ ] 255

# Question 10

Select all of the IP address ranges that cannot be issued to internet facing services, i.e. are private IP address ranges only available for communicating between two or more nodes across a private network:

 - [x] 10.0.0.0 - 10.255.255.255
 - [ ] 176.10.0.0 - 177.255.255.255
 - [x] 172.16.0.0 - 172.31.255.255
 - [x] 192.168.0.0 - 192.168.255.255
 - [ ] 127.0.0.1 - 127.255.255.255 (Is reserved for Loopback, _but_ isn't for communicating between 'two or more nodes' like the question asks)

# Question 11

What is NTP and what is it used for:

 - [ ] Node Transfer Protocol, used to move network nodes across a network.
 - [x] Network Time Protocol, used to syncronise time between nodes of a network.
 - [ ] National Telecommunication Protocol, a standard for communication across a national network.
 - [ ] None of the above.

# Question 12

Which are the default ports for HTTP and HTTPS:

 - [x] 80 and 443
 - [ ] 8080 and 8443
 - [ ] HTTP:// and HTTPS://
 - [ ] None of the above

# Question 13

Which of the following Secure-HTTP, or HTTPS, protocols are considered insecure (select many):

 - [x] SSLv1 (never released to the public, but is definitely insecure)
 - [x] SSLv3
 - [ ] SSLv8 (doesn't exist)
 - [ ] TLSv1 (TLS 1.0 is considered insecure, 1.2 is preferred.)
 - [ ] TLSv3 (doesn't exist)

# Question 14

Explain the difference betweeen TCP and UDP (2 - 3 paragraphs):

Transmission Control Protocol (TCP) provides in-sequence, guaranteed communication. The receipient tells the sender which packets it has received and the sender can verify that the receiver has the correct packets and in the correct order. The sender will re-send packets if it doesn't receive ackknowledgements in a certain time period to ensure the receiver gets all the information.

User Datagram Protocol is a 'fire-and-forget' protocol, the sender just sends packets and doesn't track if the receiver actually gets the messages or if the order is correct.

TCP is is often used when communication order and validity of the data is necessary, for example an HTTP request for a webpage.
UDP is often used for data where it doesn't matter if some data is received out of order or if some goes missing, such as log events, or if speed and little overhead is desired.

# Question 15

What is the purpose of the IP address 127.0.0.1 or hostname localhost (1 - 2 paragraphs):

Localhost is a loopback address which refers the current device. The entire 127.0.0.1/8 block is reserved although generally only the first IP in the range 127.0.0.1 is used.
This IP is often used by developers who want to run services on their own laptop for development use, such as a database, or a web server.


# Question 16

Explain the purpose of a firewall (2 - 3 paragraphs):

Firewalls monitor network traffic and attempt to stop various communications from either entering a network or moving between subnets within a network. Firewalls typically run on either layer 4 or layer 7, with layer 7 being slower but far more controlled as to the type of threats it can block as it can inspect more details about the request at the higher layer.

An example of a basic Layer 4 firewall within Azure is the Network Security Groups (NSGs) which can protect TCP/UDP traffic within a subnet, or from entering the subnet itself. This firewall may be assigned on the NIC level or on the subnet level.

An example of a Layer 7 firewall within Azure is Azure Firewall (although it operates on many layers, not _just_ layer 7) which is a FaaS (Firewall as a Service) which allows for URL inspection.


# Question 17

Draw or describe how DNS enables the use of web addreses such as www.amido.com:

Firstly a Recursive DNS Resolver is contacted to handle the DNS query, this has a list of the Root DNS servers and the correct one is contacted, in this case `com.`.

Next the Root DNS server is contacted and the domain is looked up within the server to find the Authoritative Server for the domain in question `amido.com.` in this case.

Then the Authoritative Server is contacted to find the record for the subdomain, this may or may not be delegated to other Authoritative Servers and may incur further lookups. Once found, the IP (or CNAME) is found for `www.amido.com.` and then returned to the Recursive DNS Resolver and finally back to the client.

The client may now do one of two things based on the returned record:
  - If an A record is returned the client may connect to the IP.
  - If a CNAME record is returned the client will then issue a new DNS request to the Recursive DNS Resolver and the process will repeat.


# Question 18

Explain the benefits of a flat network architecture over a hierarchical architecture:

Flat network achitecture is simpler to implement and maintain, often only having one switch in one location which all traffic passes through. All devices can easily see each other without having to traverse to another network or through various NATs. It's also cheaper to maintain as lot of switches aren't needed to provide the network segmentation.


# Question 19

What are the three steps in a TCP handshake:
SYN - A SYN packet is sent to the receiving end asking to start the communication.
SYN-ACK - Once received a SYN-ACK packet is sent back to the sender ACKing the previous SYN and sending their own SYN.
ACK - The sender finally sends back an ACK packet to acknowledge the handshake.

# Question 20

Explain the challenges that the Internet of Things brings to modern computer systems:

IoT is referring to the fact that nowadays lots of devices can connect to the Internet, even devices typically not associated with connecting.
Air-conditioning systems, Smart-lights, even smart fridges all now can connect to the Internet.
As a result of this, many devices more devices exist within Networks that didn't use to exist.
This poses potential security worries for various reasons, including that most of these devices utilise small, cheap computer chips which sometimes do not adhere to modern standards or don't have the computing power to be able to run application firewalls, or block suspicious requests.
This in turn can open up a much larger attack vector within your network. Whereas years ago your home network would have just had one PC in it, it now contains several PCs, smart devices such as mobile phones, fridges, voice assistants, and much more. Each of these could spread viruses or provide attack points towards other devices on the network, or could be compromised to join a botnet and start sending malicious data to other users. Often this form of attack is designed to target multiple devices of the same type and form a botnet sometimes capable of launching a DDoS (Distributed Denial of Service) attack against a target.

With more devices needed Network and Internet access, controlling networks becomes more difficult due to more devices, ports, protocols, etc being used. Firewalls and IDSs (Intrusion Detection Systems) for example will have to deal with many, many more rules than before to cope with all the devices and their needs and protections needed.

On the subject of hacking, some devices could cause actual harm or problems if hacked to do various things, such as an air-conditioning system caused to run into overdrive, or turning smart lights off while someone is trying to see, or even hacking into a nuclear reactor and causing a meltdown, which could happen through another device on a network.

On the privacy side of things, many people worry about the data that various IoT devices capture and 'send back home', with voice assistance sending and storing voice clips on their own servers for example. Lots of these devices don't clearly advertise what information they're collecting and could be in breach of GDPR if personal data is collected without permission and reason.
