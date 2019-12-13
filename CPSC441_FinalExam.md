# CPSC 441 Final Exam

## Chapter 1

The internet is a network of networks. It's slightly hierarchical. 

There are things called "Public internet" and "Private Intranet". Public internet is the internet that is available to everyone in the public, while Private Intranet is only available to select people.

Content providers (examples) would be like Google, MSN, Facebook, Yahoo!, etc. 

ISP would be SHAW, Telus, etc.

Hosts would be computers, phones, our personal internet devices.

Here are three tiers of the internet:
* Tier 1: National/International coverage
* Tier 2: Regional ISP
* Tier 3: Local ISP

Another way to visualize a network is that its an infrasture that provides services to applications. All services is about delivering information from one end to another.

The Network Core is basically a mesh of inter-connected routers. When moving data, there are two general ways of doing about it.

Circuit Switching involves reserving a specific set of resources from the source to destination. There is a detected circuit for two-way communication. There is no sharing.

Packet Switching is when data is divided into packets. These packets share network resources, and there is no fixed 'circuit' or path for packets to move. The routers baically store and forward. This method uses statistical multiplexing, where bandwidth is shared, there is no fixed pattern of movement.

Packet Switching supports more users, and is lower cost for users.

The Network Edge is a part of the network that is at the 'end' of the chain (i.e. an instituional network). Basically the end systems/hosts.

When working with residential access, there are three types.

Dial-up modems use your existing telephone infrastructure. It's not "always on".

DSL (Digital Subscriber Line) uses existing telephone infrastructure as well. However, there is dedicated access and a guaranteed transmission rate. The rate is dependent on the distance, line, electrical interference, etc.

Cable Modem uses TV infrastructure. It has shared access and has a variable transmission rate.

Ethernet internet access is used in companies, universities, etc. 

There are different types of guided media. There's twisted pairs, coaxial cables, and fiber optic cables. Unguided media involves radio, satellite, LAN WiFi.

Delay is an important part of evaluating the performance of a network.

The end-to-end delay is the sum of the delay of each hop.

The delay is the sum of the processing delay, queuing delay, transmission delay, and propogation delay.

The throughput is defined as the rate of which packets are transmitted from sender to receiver. basically the min(R1, R2, ...).

In this course, we will be evaluating five main layers to the OSI Model.

* Application Layer = FTP, SMTP, HTTP
* Transport = TCP, UDP
* network = IP, Routing
* Link = PPP, Ethernet
* Physical = bits on a wire

## Chapter 2

Client: Process that initiates communication
Server: Process that passively waits to be contacted

Couple Notes:
* The Server has a pernament IP address
* The Server is always on-host
* There are Data Centers for scaling
* Clients may have dynamic IP addresses
* Don't communicate directly
* May be intermittently connected

In peer to peer networks, there is no always on server. End systems directly comunicate. Peer requests service from other peers, provide service in return to other peers. Peers may change IP addresses all the time.

The Application Layer largely focuses on defining the:
* Message structure: Type, syntax, semantics
* When to send and how to send
* Loss tolerance, throughput requirement, and delay sensitivity

The application layer passes information to the transport layer for sending, and it takes incoming messages from the transport layer.

A web page consists of objects. These objects may consist of HTML files, JPEG images, Java applets, video, etc. Each object is addressable by a URL.

HTTP is a web application layer protocol that defines how web clients request web page from web servers and how the server transfers web pages. It's TCP based. HTTP is also "stateless", as it maintains no information about past client requests.

Non-persistent Connections: Close the connection after responding the request and repeat the process for each object.

Persistent HTTP connections leave the connection open till timeout: Server leaves the connection open after sending response, and closes when not used.

Cookies are used for "keeping state".

Proxy Server: Basically a cache. COnfigure the browser to access the web via cache (proxy server). All requetss are sent to the proxy server. The cache cts both a client and server.

But why caching? HTTP is stateless. Therefore, web content is fetched from the origin server for every request even for the same content. This is redundant. 

In Electronic mail, there are several different protocols:
* Send Service: SMTP
* Receive: POP3, IMAP

In SMTP, conenctions take place in three steps: Handshaking, transfer and closure. It uses TCP and persistent connections.

In POP3, there are two modes:

* Download and keep: User agent first asks the mail server to list the size of each stored message, and then retrieves
* Download and delete: same as download and keep, but deletes afterwards

POP3 maintains some state within one session. However, doesn't maintain state across sessions.

Limitations is that there are no folders and emails must come in entirety.

In IMAP, email folders are allowed, and state is kept across sessions. And you no longer need to download emails in entirety.

DNS is the Domain Name System. It maps the IP address to host names. In the application layer, it resolves names.

To resolve these names, there are two types of queries. 

Iterated queries: Contacts local name server, root DNS server, TLD server, and then authoritative DNS server.

Recursive Queries: Contacts the local name server, which contacts the root, whic h contacts TLD, which contacts DNS, done recursively.

In P2P Architecture, a peer can be both a server and a client. Peers are invited to share their upload bandwidth. It alleviates the bandwidth demand on the server.

## Chapter 3

In the transport later, the process-to-process logical communication is handled.

Multiplexing is when you get information from multiple sockets, and develop this data with a header. Then you provide the network layer sourcce with source and destination IPs.

Demultiplexing, on the receiver side, is when it examines the destination port number in the segment and delivers the segment to the application via the corresponding socket.

A host may support many simultaneous TCP sockets. Each TCP socket is identified by 4-tuples: (src IP, src port, dest IP, dest port)

UDP sockets are identified with a two-tuple (dest IP, dest port)

Link Utilization: (L/R)/(RTT+L/R) : The fraction of time that a link is actually transmitting data.

TCP:
* Connection-oriented, reliable, in-order delivery
* Process-to-process communication
* Congestion Control = to not overwhelm the network
* Flow Control = to not overwhelm the receiver

## Chapter 4

Network Layer: Routing of datagrams from the source to destination

Routing involves all network routers, whose collective interactions via routing protcols determine the paths that packets take on their trip from source to destination.
Forwarding involves the transfer of a packet from incoming link to outgoing link within a single router.

The control plane handles the network wide logic. Determines how the datagram is routed among routers along end-end path from source host to destination host

The data plane is a local, per router function. It determines how datagram arriving on router input is forwarded to the output port. 

There are three types of switch fabric. 

* Memory: Traditional computers with switching under direct control of the CPU. Packet copied to systems memory.
* Bus: Datagram from input port memory to output port via shared bus. 
* Crossbar: Overcomes bus bandwidth limitations

# Last Hours Review

The following are the levels to the OSI Model being studied in this class:
* Application Layer (HTTP, SMTP, POP3, IMAP)
* Transport Layer (Process to Process communication - TCP, UDP)
* Network Layer - (IP, routing protocol)
* Link Layer - (PPP, Ethernet)
* Physical Layer

Let's investigate the Network Layer.

The network layer can be separated into two different planes. The data plane, and the control plane.

### Data Plane

In each router, the header fields of all IP datagrams are inspected. The sender encapsulates the segments into datagrams, and the receiver delivers the datagrams to the transport layer.

Routing basically involves all the network routers, and the collective action of all of them determine the path that the packets will take.
Fowarding involves the transfer of a packet from an incoming link to the outgoing one.

The data plane is a local, per-router function. Determines how the datagram is forwarded to the output port from the input port.

The control plane is network wide logic and detemrines how datagram is routed end-to-end from the source to the destination.

Inside a Router, we have several parts. We have the routing processor, and a switching fabric as well.

In the input port, you're given the lookup (which is the destination IP and port), trying to complete processing at "line speed", and queuing (if datagrams arrive faster than forwarding rate).

In the output port, buffering (if datagrams arrive faster than transmission), and scheduling.

There's three types of switching:

* Memory - Traditional computers under direct control of CPU. The packet is copied to the system memory and speed limited by memory bandwidth
* Bus - Datagram from input port memory to output port via shared bus. Switching speed limited by the bus bandwidth
* Crossbar - Tries to overcome the bus bandwidth limitations

In the input and output ports of the router, overflow may occur which would lead to dropped packets.

HOL blocking - queued dratagram at the front of queue prevents others in the queue from moving forward. 

SCHEDULING decides which packets to drop.

When the IP datagram MTU size is bigger than the capacity of the link, we have to do what is called IP fragmentation.

The IPv4 is a 32-bit identifier for each host/router interface. A router typically has multiple interfaces, and the host typically has one interface.

The IP address is usually configured by the system administrator, and the DHCP (Dynamic Host Configuration Protocol) allows a host to dynamically get its IP address when joining the network.

The subnet part of the IP address comes from the IDP provider. 

When converting from IPv4 to IPv6, not all the routers need to be upgraded simultaneously. However, loss of header info make occur during the conversion.

Each router comes a flow table that is computed and distributed by a logically centralized routing controller. SDN is basically what this is, which allows a central control.

## Control Plane

Let's review the control plane.

There are two different routing algorithms associated with the Control Plane. 

There are the "Link State" algorithms (Dijsktra's) and the Distance Vector (Bellman-Ford) ones.

In link state, the information is global and all routers have complete topology.

In distance vector, there is decentralized information.

When routing on the internet, there are two main types of routing as discussed below.
* OSPF
* BGP

Autonomous Systems (AS) are routers in the same region.

For Inter-AS routing, there are two protocols. 

* RIP - Routing Information Protocol - Distance Vector. This is used for lower tier ISPs.
* OSPF (Open Shortest Path First) - Link State. Used for upper-tier ISPs.
* IGRP - (Interior Gateway Routing Protocol) - Distance vector, used to overcome limitations in RIP.

* BGP - Border Gateway Protocol

In the OSPF (Open Shortest Path First Protocol), a router constructs the complete topological map of the entire Autonomous Systems (AS). Each area runs its own OSFP link state algorithm. The internal details remain invisible to the outside.

Couple Features of the OSPF 
* Security - All messages are authenticated
* Mutliple same-cost paths allowed
* For each link, multiple cost metrics for different types of service
* Hierarchical OSPF in large domains

What about the BGP?

BGP makes sure that all the ASes in the internet know about each subnet and how to get there. Destinations are no longer hosts but are CIDRized prefixes which each prefix representing a subnet or a collection of subnets.

BGP provides means to:
* Obtain subnet information from neighbouring ASes
* Propogate reachability info to all AS internal routers
* Determine good routes

Terminology: 
* AS-PATH: ASs visited by the advertisement message
* NEXT-HOP: specific internal AS router to next-hop

In the SDN Control Plane (Software Defined Networking), this plane controls the routing of the entire network. The good things about a logically centralized control plane is the following:
* Easier network management - avoid router misconfigurations
* Table based forwarding (OpenFlow API) allows programming routers
* Centralized programming easier
* Distributed programming is harder

In the OpenFlow Protocol, the communication between the controller and the switches is governed. TCP is used to exchange messages. There are three classes of OpenFlow Messages:
* Controller-to-Switch
* Asynchronous (switch to controller)
* Symmetric (misc)

In switches to controller, the packet-in (transfer packet to controller). Flow removed - table entry removed. And then the controller is informed of change.

In Controller to Switches, 
* Features: Controller queries/sets switch features
* Configure: Controller queries sets switch configuration parameters
* Modify-state: add, delete, modify flow entries
* Packet-out: controller can send this packet out a specific switch port

## Link layer

The link layer is implemented in the "adaptor". Basically in the network interface card -- NIC.

The datagram is transferred by different link protocols over different links. It encapsulates datagrams into frames. 

It provides reliable delibery and flow control between adjacent nodes. There is error detection and correction.