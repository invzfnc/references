Notes are based off Networking All-in-One for Dummies (7th edition)

#### Network
Network: Nodes (devices) connected either by cable or a wireless radio connection so that they could exchange information

Information shared includes files, programs, and resources (eg printers, hard drives)

#### Client and Server
Network with clean line of demarcation: Server is solely server, clients are solely clients
Peer to Peer (P2P): A computer can be the server and the client at the same time

#### Inner Workings for a Typical Network
- Network interface: Either external jack where network cable is plugged into, or a wireless network interface, an antenna
- Network cable: Plugs into the network interface card (NIC) at the back of computer. The type that is commonly used is the twisted-pair cable
- Network switch: Connects computers to form LAN
- Network router: Connects networks to form larger network. eg. Connects to the Internet. Switch and router are usually combined into a single device.

Wireless networks
- Flexible
- Less secure - Potential unauthorized interception
- Less faster than wired networks
- Less stable than wired networks

#### Types of Networks
LAN (Local Area Network): Computers within same office or building
WAN (Wide Area Network): Office in San Francisco and office in New York
MAN (Metropolitan Area Network): Smaller than typical WAN but larger than LAN

#### Topology
##### Bus Topology
Nodes are strung together in one line
Every node on the network can see every packet that's sent on the cable
If one cable breaks, the whole network is disabled

##### Star Topology
Each node is connected to a central device, hub/switch
If a cable breaks, only the node connected is isolate from the network, the others can continue without interruption

Hub: Doesn't know anything about computers, duplicates packets and send them to all ports/nodes
Switch: Sends received packet to its receiver/port the receiver connected to

Stars can expand, connect a switch to another switch as if it is a node

##### Ring Topology
Packets are sent around the circle from computer to computer, each computer looks at the packet to decide whether the packet was intended for it, if not, the packet is passed to the next node in the ring

##### Mesh Topology
Multiple connections between each node on the network, provides alternative routes if one cable breaks
Mesh networks are common for MAN and WAN, routers are arranged in a way that provide multiple paths between two nodes
