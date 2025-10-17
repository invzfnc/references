|TCP, Transmission Control Protocol|UDP, User Diagram Protocol|
|---|---|
|Guarantees the delivery of data to the destination router|The delivery of data to the destination cannot be guaranteed|
|Has extensive error-checking mechanisms|Has only the basic error-checking mechanisms using checksums|
|Uses handshakes such as SYN, ACK, SYN-ACK|Connectionless protocol, no handshake|
|Doesn't support broadcasting|Supports broadcasting|
|Retransmission of lost packets is possible|There is no retransmission of lost packets|
|TCP is comparatively slower than UDP|UDP is faster, simpler, and more efficient than TCP.|
|Communications standard for **delivering data** and messages through networks|Communications protocol for **time-sensitive** applications like gaming, playing videos, or Domain Name System lookups|

netcat: Computer networking utility for reading from and writing to network connections using TCP or UDP.