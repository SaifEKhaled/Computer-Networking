# Computer Networking Notes
## (Still getting updates regularly)
Welcome to the Computer Networking notes! This README file contains all the chapters covered so far. You can click on any chapter to jump directly to its section.

## Table of Contents
- [Chapter 1: Introduction to Computer Networking](#chapter-1-introduction-to-computer-networking)
- [Chapter 2: ...](#chapter-2-placeholder-for-next-chapter)

---

## Chapter 1: Introduction to Computer Networking

We (users) are hosts, and we run networks apps on the Internet's edge. hosts can be desktops,tablets,laptops...etc. but how the traffic gets forwarded/directed? it's by the help of packet switches. which breaks the data into chunks of data (later be called packets). sends them independently on the internet and share resources dynamically. examples of packet switches : routers. and how to connect these packet switches with each other, you may wonder? with the help of *Communication Links*! such as (Fiber,Copper, Radio, Satellite) and its unit is *Bandwidth* (the transmission rate). with the collection of the previous mechanics. we have a Network! that's managed by an organization.

## to sum things up: 

**Hosts**: End systems like users' devices (desktops, tablets, laptops, etc.).

**Packet Switches**: Devices that forward/direct traffic by breaking data into chunks (packets). Example: Routers.

**Communication Links**: Used to connect packet switches (e.g., fiber, copper, radio, satellite). Unit: **Bandwidth** (transmission rate).

**Networks**: A collection of devices, routers, and links. Networks form the **Internet** when interconnected.

### Protocols

Clear so far? so bunch of networks connected with each other forms us the *Internet*, which is basically an interconnected Internet Service Providers (ISP) with each other. This may seem complex a little bit, that's why we needed a *Protocol*. Protocol is basically a system of rules. that are strictly adhered and should be followed in order to complete a procedure. for example, we humans apply the form of protocol in our daily life! we have an objective (for example, a meeting) , we need to choose a time and place, getting ready for the meeting and going to the meeting. That's a protocol! Internet also have a protocol to finish certain tasks. such as Controlling and Receiving Messages. these important tasks need a protocol so it can be controlled as needed. such as HTTP in Web Browsing, TCP (Transmission Control Protocol) that ensures the data sent across the network reaches its destination reliably.

- **Protocol**: A set of rules defining the format, order of messages sent and received, and actions taken. Examples: HTTP for web browsing, TCP for reliable data transfer.
  
### Internet Structure

The internet is divided into three main parts:
1. **Network Edge**: Hosts like clients and servers.
2. **Access Network**: Wired and wireless communications.
3. **Network Core**: Interconnected routers forming the internet backbone.

### Access Networks
In Access Networks, they were initially made by using an existing telephone lines to a central office. in internet access, the internet data travels in higher frequencies and it gets handled by DSL modem and DSLAM, then sent to internet. However, in traditional voice calls: it travels over lower frequencies and sent to traditional telephone network.

- **DSL**: Uses existing telephone lines for internet data at higher frequencies. Voice calls use lower frequencies.
- **Wireless Access Networks**:
What are wireless access networks? It's a way that connects end system to router by an access point. and it has two types:
  - **WLAN**: Local, in-building.
  - **Cellular Networks**: Wide-area, mobile.
Moreover, Enterprises uses the same concept, but in larger scale. they mix between wired and wireless technologies by connecting a mix of switches and routers.
- **Wired connection** : Ethernet (Usually has higher speed)
- **Wireless Connection**: WiFI

#### _Note : To connect hundreds of servers together, you need high bandwidth links._

### Packet Transmission

**Hosts' Role**:
- Receives application messages.
- Breaks data into packets of length **L**.
- Sends packets over access networks at rate **R**.

Formula for Packet Transmission Delay:  
`Packet Delay = L(bits) / R(bits/sec)`

### Network Core
it's a mesh interconnected routers uses packet switching as we unraveled earlier. but it can use another way called Circuit Switching.
- **Packet Switching**: Independently routes packets over shared resources, data may be queued before being transimitted, congesition loss, resources on demand not reserved. (avg low generates high)
- **Circuit Switching**: Pre-establishes a path, ensuring resource sharing but may waste bandwidth, reserves resources, multiplexing,telephone call (avg same generates same)

### Network Functions
The Network has 2 Functions:
- **Forwarding/Switching** : a local action => moves the input packets into the appropriate router output link
- **Routing**: a Global Action => determine source-destination paths taken by packets

## Network Layering:
The Network is complex, huh? and the more you delve in it the more it gets complex. That's why the internet engineers decided to approach these systems with an approach called Layering. this will ease maintenances and system updates. So, what's layering? Layering is basically the identifying of system pieces and the relationship between them.

### Layers of the Internet Protocol Stack

1. **Application**: Supports network apps (e.g., HTTP).
2. **Transport**: Process-to-process data transfer (e.g., TCP).
3. **Network**: Routes datagrams from source to destination (e.g., IP).
4. **Link**: Transfers data between neighboring network elements.
5. **Physical**: Transfers bits over a physical medium.

#### Additional ISO/OSI Layers:
6. **Presentation**: Data interpretation (e.g., encryption, compression).
7. **Session**: Synchronization and recovery of data exchanges.

so why are both of these layers are missing on the internet stack? actually, the engineers found out that if the services that are offered by them are needed, it must be implemented in the application, if not, then no biggie! 

**Memorization Tip**:  
`A`ll (Application)
`P`eople (Presentation)
`S`eem (Session)
`T`o (Transport)
`N`eed (Network)
`D`ata (Data Link)
`P`rocessing  (Physical).

### Encapsulation in the Internet Protocol Stack

1. **Application Layer**: Sends messages.
2. **Transport Layer**: Adds transport header to create a segment.
3. **Network Layer**: Adds network header to create a datagram.
4. **Link Layer**: Adds link header to create a frame.

### Packet Delays

**1- Application Layer** => exchange Messages using services of transport layer (now holds M "Message" ) then it goes to =>
**2- Transport Layer** => Transfers Messages from one process to another, using services of network layer (it encapsulates the previous M with H.t "Transport Layer header" to create a transport-layer segment) then it goes to =>
**3- Network Layer** => transfers the previous segment from one host to another using link layer services (it encapsulates the previous H.t | M with H.n "Network Layer-Layer header" to create a Network-layer datagram) then it goes to =>
**4-Link Layer** => transfers datagram from host to neighboring host using network-layer services (it encapsulates the previous H.n | [H.t | M] With "Link Layer header" H.i to create a link-layer frame)

### Packet Switching: Store-and-Forward & Queuing

- **Store-and-Forward**: A router must receive the entire packet before transmitting it to the next link.
- **Queuing**: If the arrival rate of packets exceeds the transmission capacity, packets will queue, and some may be **dropped** if the buffer fills.

### Internet Structure

**Hosts "access nets"** => Connects to => **Regional ISP connects** => Connects to => **ISP** => connects to => **Internet Exchange Point (multiple ISPs are connected)**

### Nodal Packet Delay

The **Total Delay** (or **Nodal Delay**) at a router is:

Total Delay = d_proc + d_queue + d_trans + d_prop
Where:
- `d_proc` = Processing Delay (checks bits errors, determine output link , speed: less than microsecs).
- `d_queue` = Queuing Delay (time waiting for the output link, speed: depends on congestion level of router).
- `d_trans` = Transmission Delay (time to send packet bits onto the link) => L(length of packet)/R(Transmission Rate)
- `d_prop` = Propagation Delay (time for the signal to travel the physical link) => d(Distance)/s(Propagation Speed)

**Packet Queuing Delay** = (Length of packet * average packet arrival rate)/Rate = `(L*a)/R` 

=> if `(L*a)/R` ~ 0 => small delay  
=> if `(L*a)/R` = 1 => large delay  
=> if `(L*a)/R` > 1 => infinite delay  
                                                                             
---

### Throughput

Throughput is the rate at which bits are successfully transmitted between sender and receiver. The end-to-end throughput is constrained by the slowest link along the path:

Where:
- `R_s` = server-to-network link capacity.
- `R_c` = client-to-network link capacity.
the lesser one limits the average end-to-end throughput.
---
## End of Chapter 1



[Back to Top](#table-of-contents)
