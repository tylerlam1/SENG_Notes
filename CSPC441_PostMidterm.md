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

