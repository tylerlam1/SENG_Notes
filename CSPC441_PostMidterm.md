# CPSC 441 Post-Midterm

## OSI Model
The simplified OSI Model has the following five layers:
* Application Layer - Directly supports network applications (FTP, SMTP, HTTP)
* Transport Layer - Process-to-process data transfer (TCP, UDP)
* Network Layer - Routing of datagrams from source to destination
* Link Layer - Data Transfer between neighbouring network elements
* Physical - Bits on a wire

## Host-to-Host communication
When hosts communicate, the router examines header fields of all IP datagrams passing through it. Routers do not run (or check) the application and transport layer.
* The sender encapsulates segments into datagrams
* The receiver delivers datagrams to the transport layer

## Routers

* Routing involves all network routers, whose collective interactions via routing protocols determine the paths that packets take on their trip from source to destination (network-wide process).
* Forwarding involves the transfer of a packet from an incoming link to an outgoing link within a single router.

## Data Plane vs the Control Plane

* The Data plane is a local per-router function. It determines how datagrams arriving on router input port is forwarded to router output port.
* The control plane is the network wide logic which determines how datagrams are routed among routers along end-to-end paths. There are two approaches:
1. Traditional Routing Algorithms: Implemented in routers
2. Software-defined networking: Implemented in servers

### Per-Router Control Plane
Individual routing algorithm components in each and every router interact on the control plane.

### Logically centralized Control Plane
A distinct controller interacts with the local control agents. Basically this remote controller controls the routing algorithms that go on.

## Inside a Router
Routing management control plane operates in the millisecond time frame.
Forwarding Data Plane operates in the nanosecond timeframe.

## Router Architecture
Input/Output ports perform functions in the network layer, link layer and physical layer.

Couple of terms:
1. Input Port:
* Lookup: Given the datagram dest IP and port or header information
* Goal: Complete input port processing at "line speed"
* Queuing: If datagrams arrive faster than the forwarding rate
2. Output Port:
* Buffering/Queuing: If datagrams arrive from switch fabric faster than the transmission rate
* Scheduling: Choose among queued datagrams for transmission
3. Switch Fabric
* This connects the routers input to its outputs
4. Processor
* The routing processor executes the routing protocol, maintains the routing information and forwarding tables, and performs network management functions.

## Switch Fabric

The switch fabric packets info from input to output ports.

The switch fabric can be implemented in three different ways.

1. Memory - Tradition computers with switching under the direct control of the CPI. The packet is copied to the systems memory, and the speed itself is limited to the memory bandwidth.
2. Bus - Datagram from input port memory to output port memory through a shared bus. Therefore, the switching speed is limited by the bus bandwidth.
3. Crossbar - This overcomes the bus bandwidyh limitations. Basically fragments datagram into fixed length cells, switch cells through teh fabric.

### Queuing
Queues can form at both the input and output ports. The buffers can always overfloe and packets are dropped.
* HOL (Head-of-the-Line) blocking: queued datagram at the front of queue prevents other packets from moving forward

## Loss and Congestion at Routers

Congestion: When the enqueuing rate is faster than the dequeuing rate on either side of the fabric.
Loss: When the buffer is full, packets are dropped.

## IP Fragmentation

* Different link types may have different sizes for MTU (maximum transmission unit)

## IPv4 Addresses

223.1.1.1 = 11011111 00000001 00000001 00000001

The first three sections are the subnet part and the last section is the post hart.

The IPv4 address is a 32-bit identifier for each host/router interface.
* Interface: Connection between host/router and physical link

### Subnets

* Device interfaces with the same subnet part of IP address can physically reach out to each other without intervening router
* A isolated network is called a subnet

## IP Addresses

* IP addresses are configured from the system admin. The Dynamic Host Configuration Protocol (DHCP) allows a host to dynamically obtain its IP address from the DHCP server when it joins the network
* DHCP can renew its lease on address in use, allows reuse of addresses, allows host to learn additional information such as subnet mask, the address, and DNS server

### Hierarchical address

* The network can get the subnet part of the IP address by getting the allocated portion of its provider ISP's address space
* The ISP can get a block of address via ICANN: Internet Corporation for Assigned Names and Numbers

## NAT

* Network Address Translation - All the devices in the same network IP address
* Advantage: flexibility - The IP addresses can change on either side of the network without impacting the other side
* Advantage: Protection - The devices are not explicitly addressable from outside

## IPv6

IPv4 has a 32-bit address space. This means that there is 2^32 addresses, which is a lot.

We need a better header format for speed processing and QoS support.

## IPv4 and IPv6

* Not all routers can be upgraded simultaneously
* Loss of header information due to conversion between IPv4 and IPv6.
* Takes time to convert

### Tunnelling

IPv6 carried as payload in IPv4 datagram among IPv4 routers

## Generalized Forwarding and SDN

Each router contains a flow table that is computed and distributed by a logically centralized routing controller

## OpenFlow data plane abstraction

* Flow: defined by header fields
* Generalized forwarding: simple packet-handling rules
* Match: match values in packet header fields
* Actions: drop, forward, modify, matched packet or send matched packet to controller
* Priority: disambiguate overlapping aptterns