Standards and protocols provide a precise sequence of steps that each element of a network must follow to enable communications

Protocol defines format

Internet Protocol defines the format of IP addresses, four 8-bit octets whose value ranges from 0-255, eg `10.0.101.155`

#### Open Systems Interconnection (OSI)
Layers
1. Physical (Cables, connectors, repeaters, network interfaces)
2. Data link (Techniques to uniquely identify devices, switches, MAC addresses)
3. Network (Routing data across network, routers)
4. Transport (Data packets)
5. Session (Establishing sessions)
6. Presentation (Converts data so systems that use different format can exchange information)
7. Application (Allow applications to request network services)

Term:
Adapter == interface == port

#### MAC Addresses
Or physical addresses
Each network interface must have a unique identifier called MAC (media access control) address 
48-bits, 6 octets separated by hyphens
eg `48-2C-6A-1E-59-3D`
MAC addresses are associated with the network interface, not with the device that uses the interface

#### Packets
Structure of standard packet
1. Preamble (56-bit, to synchronize the precise timing required to read packet data)
2. Start of frame marker (1 byte)
3. Destination MAC address (6 bytes)
4. Sender MAC address (6 bytes)
5. Tag (Optional, for VLANs)
6. Ethertype (Specific protocol contained in the payload, 2 bytes)
7. Payload (Actual data, 46-1500 bytes, is almost always created by a high level protocol such as IP)
8. Frame check sequence (To verify/check that frame data was sent correctly, 4 bytes)

Collisions happen when two or more computer try to transmit a packet at the same time

Broadcast packets, with destination MAC address `FF-FF-FF-FF-FF-FF`, are intended to be received by every device on the network

#### Wireless Networks
Rather than switches or hubs, wireless devices connect to a wireless access point (WAP)
WAPs are essentially hubs, every device that connects to the access point is competing for the same bandwidth, all devices connected to the access point must inspect the packet to determine the MAC address destination
If two devices try to send packets at the same time, collision occurs, this is one of the reasons wireless networking is slower than wired networking