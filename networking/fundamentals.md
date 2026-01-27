# Networking Fundamentals

This file documents core networking concepts studied as part of my foundational
networking learning.

---

## TCP/IP Model

The TCP/IP model is a conceptual framework used to understand how data is
transmitted over networks. It consists of **four layers**:

1. **Application**
   - Provides network services to applications
   - Examples: HTTP, HTTPS, FTP, SMTP, DNS

2. **Transport**
   - Responsible for end-to-end communication
   - Handles reliability and flow control
   - Examples: TCP (reliable), UDP (connectionless)

3. **Internet**
   - Responsible for logical addressing and routing
   - Example: IP (Internet Protocol)

4. **Network Access**
   - Handles physical transmission of data
   - Includes hardware addressing and framing
   - Examples: Ethernet, Wi-Fi

The TCP/IP model is more practical and widely used than the OSI model.

---

## Encapsulation

Encapsulation is the process of wrapping data with protocol-specific information
as it moves **down the OSI model layers** before being transmitted over a network.

Each OSI layer adds its own information to the data in the form of headers
(and in some cases trailers).

### Encapsulation across OSI layers:

1. **Application Layer (Layer 7)**
   - User data is created by applications
   - Examples: HTTP requests, emails, file transfers

2. **Presentation Layer (Layer 6)**
   - Data is formatted, encoded, or encrypted if required

3. **Session Layer (Layer 5)**
   - Manages sessions and connections between devices

4. **Transport Layer (Layer 4)**
   - Adds TCP or UDP headers
   - Handles segmentation, reliability, and port numbers

5. **Network Layer (Layer 3)**
   - Adds IP header
   - Responsible for logical addressing and routing

6. **Data Link Layer (Layer 2)**
   - Frames the data
   - Adds MAC addresses and error detection

7. **Physical Layer (Layer 1)**
   - Converts data into electrical, optical, or radio signals
   - Transmits bits over the physical medium

When the data reaches the destination, the process is reversed
(**decapsulation**) as each layer removes its corresponding header.

Encapsulation allows:
- Clear separation of responsibilities between layers
- Interoperability between different hardware and software
- Easier troubleshooting and packet analysis


---

## Network Topologies

A network topology describes how devices are connected within a network.

### Common topologies:

#### Bus
- All devices share a single communication line
- Simple but prone to collisions

#### Star
- Devices connect to a central switch or hub
- Easy to manage and troubleshoot
- Most common modern topology

#### Ring
- Devices form a closed loop
- Data travels in one or both directions

#### Mesh
- Devices are interconnected
- High redundancy and fault tolerance
- Common in critical or large-scale networks

#### Hybrid
- Combination of multiple topologies
- Used in real-world networks

---

## Notes
- OSI and TCP/IP models describe similar concepts at different abstraction levels
- Understanding encapsulation helps with packet analysis and troubleshooting
- Topology choice affects performance, scalability, and reliability
