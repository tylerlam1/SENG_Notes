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