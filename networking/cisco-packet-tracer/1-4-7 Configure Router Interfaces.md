**assign ipv4 addresses to R1 and LAN devices**  
```
R1>enable
R1#configure terminal

R1(config)#interface g0/0
R1(config-if)#ip address 172.16.20.1 255.255.255.128
R1(config-if)#no shutdown

R1(config-if)#interface g0/1
R1(config-if)#ip address 172.16.20.129 255.255.255.128
R1(config-if)#no shutdown
R1(config-if)#
```
refer to the addressing table provided for interface mapping