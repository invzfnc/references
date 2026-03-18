`R1# show ip interface brief | exclude unassigned` - display interface designations, IP address and status  

Output:
```
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0/0   172.16.20.1     YES manual administratively down down 
GigabitEthernet0/0/1   172.16.20.129   YES manual up                    up 
Serial0/1/0            209.165.200.229 YES manual up
```
GigabitEthernet0/0/0 is down, to enable it

```
R1#enable
R1(config)#interface g0/0/0
R1(config-if)#no shutdown
```

Verify the IP addresses configured on R1
```
R1#show running-config
...
interface GigabitEthernet0/0/0
 description Connection to SW1
 ip address 172.16.20.1 255.255.255.128
 duplex auto
 speed auto
!
interface GigabitEthernet0/0/1
 description Connection to SW2
 ip address 172.16.20.129 255.255.255.128
 duplex auto
 speed auto
!
interface Serial0/1/0
 description Circuit ID BCB123450001
 ip address 209.165.200.229 255.255.255.248
 clock rate 2000000
```
IP address and subnet mask interface Serial0/1/0 is incorrect (refer to addressing table provided, should be 209.165.200.225)

```
R1(config)#interface serial0/1/0
R1(config-if)#ip address 209.165.200.225 255.255.255.252
```

`R1# show ip route | begin Gate` - Display routing table by filtering to start the output at the word Gateway

```
R1# show interface | include Desc|conn
GigabitEthernet0/0/0 is up, line protocol is up (connected)
  Description: Connection to SW1
GigabitEthernet0/0/1 is up, line protocol is up (connected)
  Description: Connection to SW2
Serial0/1/0 is up, line protocol is up (connected)
  Description: Circuit ID BCB123450001
R1#
```

```
R1#show interfaces gigabitEthernet 0/0/0 | include duplex
  Full-duplex, 100Mb/s, media type is RJ45
```