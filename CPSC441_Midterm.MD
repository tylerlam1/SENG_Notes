# CPSC 441 Midterm Review
## Chapter 1

### What is the Internet?
The internet is a network of networks
* It is loosely hierarchical - Computers in one location can connect to computers in a different location with the help of protocol stacs (i.e. protocol layer, transmission control layer, internet protocol layer, hardware layer)
* Public Internet is internet that everyone has access to. 
* Private Internet is internet that only a certain group has access to.

The internet consists of millions of connected end systems/host
* Generally, a host/end system is a computer, workstation, server, email server, tablet, etc.

A router is a networking device that forwards data packets between computer networks. Routers perform the traffic directing functions on the internet. Data sent through the internet is in the form of data packets. 
### What is a Link?

A communication link provides a way for information to move between separate components. For example
* Twisted Pair
* Coaxial Cable
* Optical Fiber
* Ethernet 
* USB

### Request for Comments (RFC)

A RFC is a text document authored by engineers which describes methods, behaviours, innovations applicable to the internet. 

### Internet Engineering Task Force (IETF)

Large international community working on the envolution of the internet

### Quick Examples:
#### Content Providers:
* Google
* MSN
* Facebook
* Youtube
* Yahoo!
#### ISP 
* SHAW
* Telus
* Rogers

### Different hierarchies in the internet
#### Tier 3: Local ISPs
* This pretty much denotes the higher-tier customers
#### Tier 2: Regional ISP
* These are customers of tier 1
#### Tier 1: National ISP
* National coverage (Verizon, Sprint, etc.)

### What is a network?
A network is an infrastructure that provides services to distributed applications. It delivers information from one end to another, and is "best effort" by default.

### How does information get to you?
Information gets to you in the following manner: 
* Goes from the Content Providers
* Goes to the Global ISP
* Goes to regional ISP
* Goes to local ISP

### Network Core

The network core is basically the 'core' of a telecommunications network. It basically does all the important services, like direct phone calls, etc. It is a mesh of interconnected routers.

### Circuit Switching
In a circuit switching network, a connection must be established before transmitting. A certain bandwidth is reserved from the source to the destination. A dedicated circuit is created for two way communication, and there is no sharing. A circuit/connection must be established before any communication sharing.

1. First the end host looks for a acceptable connection from the source to the destination
2. Once found, the connection is established
3. The host 'rents' the line until the connection is broken

This is why long distance calls are so expensive

### Packet Switching
Data is divided into packets. Packets share network resources (bandwidth), and there is no fixed path for delivering packets and resources are used on demand. Routers store and forward the information.

1. The data splits itself in packets
2. Packets travel in any direction, and make their way to the destination
3. The packets reassemble at the destination

### Store and Forward
1. Packets arrives on one link and are fowarded to another link
2. The entire packet must arrive at the router before transferring to another link

### Statistical Multiplexing
* Sequence of packets
* No fixed pattern
* Bandwidth shared on demand

Packet switching is better as it supports more users and is a lower cost for users.

### Network Edge
The network edge is the point where a network connects to a new third-party network. End systems/hosts are also on the "edge" of the network

### Residential Access
#### Dial-Up Model

Uses the telephone to connect to the internet

### Digital Subscriber Line

Uses the telephone infrastructure to connect to the internet

### Cable Modem

Uses the cable TV infrastructure

### Institutional Access
* Ethernet Internet Access
* Used in companies, universities
* End systems connect to ethernet switch

## Examples of Physics Media/Links
* Twisted Pair (phone wires)
* Coaxial Cable - baseband, broadband
* Fiber Optic: High-Speed
* Radio: Unguided media

When information transfers from one router to another, there is a delay.

The total-end-to-end delay is caused by the delay of each hop (from router to router)

It is the sum of:
* Processing Delay - Checking for bit errors, output link
* Queuing Delay - Waiting in the buffer
* Transmission Delay: Packet length/ Link Bandwidth
* Propagation Delay: Length of physical link/propogation speed

### Potential causes of packet loses
* The buffer at routers have a finite capacity
* Packet arriving at a full queue may be lost
* A lost packet may be transmitted again...


### Tranmission Time and Throughput
Transmission Time - Time taken to transmit a sequence of bits
Throughput - The rate at which the bits are transmitted from sender to receiver
Is calculated by min(R1, R2,...)

### Communication Protocols
* Protocols control the sending and receiving of messages
* Protocols define format, order of messages sent and received

### Different Protocol Layers
* Application - Supporting network applications
* Transport
* Network
* Link
* Physical

Please note that each higher level relies on the level below

## Review Questions

A host is basically a system like a computer, router -> anything that has a IP address.
A router is a networking device used to forward data packets to other routers. These form networks, which form the internet.
Circuit switching is good in that fact that there is less chance of lost packets. In addition, the data packets process faster.
However, packet switching is less expensive, and does not require a set bandwidth/connection.

Packet switching is being relied on nowadays because its less expensive, and much more efficient use of bandwidth. With some many people connected to the internet, it is much more efficient to use packet switching. 

DSL is fixed transmission rate because there is dedicated access.

Cable modem has a variable transmission rate because there is shared access.

Guided media are links that are 'solid' like cables, links, etc. Unguided media are things like radio waves.

## Chapter two

### Processes

A process is a program that runs within a host.
* Within he same host, two processes can communicagte using inter-process communication
* Processes in different hosts communicate by exchanging messages

* A client is a process that initiates communication
* A server is a process that waits to be contacted.

### Client Server Architecture
Server
* The server is always on
* There is a pernament IP address
* There are data centers for scaling

Clients
* Communicates with server
* May be intermittently connected
* Changing IP addresses

### Peer-to-Peer networking
* There is no always-on server
* Arbitrary end systems communicate directly
* Peers request service from other peers
* Change IP addresses

### Application Layer Protocol
* Public Domain protocols (HTTP, SMTP) - HTTP pulls the information from the server (Hyper Text)
* SMTP pushes the information to the server (Simple Mail)
* Proprietary protocols - Protocols owned by a single organization (Skype)
* Application Layer is the one part of the network application that defines the messagr structure (type, syntaz, semantics), when to send and how to send, loss tolerance, throughput, delay
* The application alyer passes the message to the transport layer for sending, and takes incoming messages from the transport layer

### Transport Layer 
* There is reliable/unreliable data transfer
* For example, no-loss applications exist like file tranfer
* Loss tolerance ones like audio

In the transport layer, there is the TCP and UDP services.

The TCP service is where a service can send and receive at the same time. It has reliable transport, and contains flow control (sender won't overwhelm receiver). Congestion control offers to throttle sender when network is overloaded. However, there is a minimum throughput guarantee, and no timing guarantee.

UDP service is where there is unreliable data transfer between the sender and receiver. It doesn't provide congestion control, flow control, congestion control, but is very light weight and is better used for loss tolerant applications.

Examples of TCP
* Email
* TCP
* Web
* TCP

Examples of UDP
* Streaming
* telephony


### Web Pages

A web page consists of objects. These objects can be HTML files, JPEG images, applets, audio, video. Each object is addressable by a URL.

### HTTP

HTTP is a web application layer protocol that defines how web clients request web pages from web servers and how servers trasnfer web pages to clients
Client: Web browser
Server: Web server
TCP Based

In a normal HTTP Requests, you can use GET to retrieve content, POST to update data,...

### Persistent vs Nonpersistent Connections
*RTT = Time for small packet to travel form client to server and back

#### Non persistent connections
* Close the connection after responding the request and repeat the the process for each object

#### Persistent Connection
* Does not require connection setup over and over again.
* Server leaves the connection open after sending a response, and closes it after not being used for a certain period of time

### Cookies

Cookies keep the state. With cookies, states can be maintain at the sender and the receiver over multiple transactions.

The HTTP cookie is a packet of data that a computer receives and sends back without changing it. For example, when you visit a website, the computer stores it in the web browser. This is to help the website keep track of your visits and activity (like items in the sjopping cart). Or could be save login information.

### Conditional GET

* The conditional GET handles clients requests without involving origin server
* It configures the browser to access the web via cache
* All requests are sent to the proxy server
* Cache hit: Return the object immediately
* Cache miss: Forward to origin server

### Electronic Mail
* There are three major components to electronic mail: 
* User agents: Composing and Reading email
* Mail servers: Mailbox for each user and message queue for outgoing messages
* Protocols: SMTP (for sending), POP3 and IMAP for receving

There are three phases to the SMTP Connection.
1. Handshaking
2. Transfer
3. Closure

It uses TCP and persistent connections. The message is queued on the sender server if it cannot be delivered to receiver.

#### POP3

There are two modes for POP3. 
1. Download-And-Keep: User agent asks the mail server to list the size of each stored message, and then receives
2. Same as Download-And-Delete, but the user agent deletes each message

POP3 maintains state information during a POP3 session, but is stateless across sessions

#### IMAP

Keeps all mesages on the server. Allows for organized messages in folders, & search.
IMAP keeps user state across sessions.
Users can download the header or just one part of the MIME message.

#### HTTP
* Using the browsers as email clients allows communication with the mail server.

### DNS - Domain Name System
* Maps between the IP addresses and host names
* host aliasing (associate a service to a host alias)
* Multiple hosts ashare one IP address or multiple IP addresses associated to one host name
* The application layr protocol usually resolve names
* Distributed database implemented in a hierarchy of many DNS servers

### DNS Servers
* Root DNS servers are contacted by a local name server when it cannot resolve name
* Contacts the TLD name server if name mapping not known
* Top LEvel Domain (TLD) DNS servers: run the com org net, top servers, etc.
* Authoritative DNS Servers: oRGANIZATIONS dns SERVERS PROVIDING HOSTNAME TO for IP address
* Local name servers: First point of contact for ISP

### Iterated Queries
1. The end host contacts the local name server
2. Then it hits the root DNS server (which consults the TLD)
3. The TLD then finds the authoritative DNS server
3. The name is resolved

### Recursive Queries
1. The end host contacts the local name server
2. If not resolved, it contacts the root DNS server
3. The TLD DNS server is called, which contacts the authoritative DNS server
4. The result is relayed back to host

The difference betweenr recursive queries and iterated queries is that recursive queries make DNS calls on each server on behalf of the client. In iterated, the client makes the calls itself.

### DNS Caching
TLD servers typically cached in locao name servers, thus root name servers often not visited.

RR format: (name, value, type, TTL) <- TTL means time to removal from cache>

DNS protocol is based on UDP

### Peer-to-Peer architecture
* A peer can be both the server and client
* Peers are invited to share their bandwidth


### File distribution in Client Server
The time it takes to upload a file in peer-to-peer is filesize/upload speed.

The time it takes to download a file is filesize/download speed.


### BitTorrent

The file is divided into chunks, and peers exchange chunks with each other.
The tracker tracks peers participating in torrent.
The seed: The peer/server has complete file.
Torrent: A collection for all peers participating in a file.
