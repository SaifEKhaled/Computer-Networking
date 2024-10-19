# Computer Networking Notes

Welcome to the Computer Networking notes! This README file contains all the chapters covered so far. You can click on any chapter to jump directly to its section.

## Table of Contents
- [Chapter 1: Introduction to Computer Networking](#chapter-1-introduction-to-computer-networking)
- [Chapter 2: ...](#chapter-2-placeholder-for-next-chapter)

---

## Chapter 1: Introduction to Computer Networking

### Key Concepts

**Hosts**: End systems like users' devices (desktops, tablets, laptops, etc.).

**Packet Switches**: Devices that forward/direct traffic by breaking data into chunks (packets). Example: Routers.

**Communication Links**: Used to connect packet switches (e.g., fiber, copper, radio, satellite). Unit: **Bandwidth** (transmission rate).

**Networks**: A collection of devices, routers, and links. Networks form the **Internet** when interconnected.

### Protocols

- **Protocol**: A set of rules defining the format, order of messages sent and received, and actions taken. Examples: HTTP for web browsing, TCP for reliable data transfer.
  
### Internet Structure

The internet is divided into three main parts:
1. **Network Edge**: Hosts like clients and servers.
2. **Access Network**: Wired and wireless communications.
3. **Network Core**: Interconnected routers forming the internet backbone.

### Access Networks
- **DSL**: Uses existing telephone lines for internet data at higher frequencies. Voice calls use lower frequencies.
- **Wireless Access Networks**:
  - **WLAN**: Local, in-building.
  - **Cellular Networks**: Wide-area, mobile.

### Packet Transmission

**Hosts' Role**:
- Receives application messages.
- Breaks data into packets of length **L**.
- Sends packets over access networks at rate **R**.

Formula for Packet Transmission Delay:  
`Packet Delay = L(bits) / R(bits/sec)`

### Network Core

- **Packet Switching**: Independently routes packets over shared resources.  
- **Circuit Switching**: Pre-establishes a path, ensuring resource sharing but may waste bandwidth.

### Layers of the Internet Protocol Stack

1. **Application**: Supports network apps (e.g., HTTP).
2. **Transport**: Process-to-process data transfer (e.g., TCP).
3. **Network**: Routes datagrams from source to destination (e.g., IP).
4. **Link**: Transfers data between neighboring network elements.
5. **Physical**: Transfers bits over a physical medium.

#### Additional ISO/OSI Layers:
6. **Presentation**: Data interpretation (e.g., encryption, compression).
7. **Session**: Synchronization and recovery of data exchanges.

**Memorization Tip**:  
`A`ll `P`eople `S`eem `T`o `N`eed `D`ata `P`rocessing (Application, Presentation, Session, Transport, Network, Data Link, Physical).

### Encapsulation in the Internet Protocol Stack

1. **Application Layer**: Sends messages.
2. **Transport Layer**: Adds transport header to create a segment.
3. **Network Layer**: Adds network header to create a datagram.
4. **Link Layer**: Adds link header to create a frame.

### Packet Delays

- **Processing Delay**: Time to check bit errors and determine output link.
- **Queuing Delay**: Time waiting in queue for transmission.
- **Transmission Delay**: Time to push all packet bits onto the link (`L/R`).
- **Propagation Delay**: Time for the signal to travel the distance (`d/s`).

---

[Back to Top](#table-of-contents)
