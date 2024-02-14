Switches are layer 2 devices, they can inspect packets and act based on the content (MAC address) of packets

#### Learning
When a packet is received on any port, the switch examines the MAC address of the packet and associates the (sender) MAC address with the port. The switch adds this information to the MAC address table, known as the *forwarding table*

#### Forwarding
The switch looks up to the forwarding table and sends the packet out to the corresponding port. This is called forwarding

Switches have memory buffers for each port to store the entire packet before forwarding to its destination port

#### Flooding
When a switch receives a packet where its receiver MAC address is not in the forwarding table, the switch simply forwards the packet to all ports other than the sender port, this is called flooding.

There is a good chance that the the destination device will receive the packet and send a reply back to the sender. The switch will record the MAC address of this recipient on its table.

