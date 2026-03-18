Uses 1x 1941 router, 2x 2960 switch, 2 PCs, copper straight-through cables

Rename display names: Click text label and enter new display name

Connection:

|From|Port|To|Port|
|---|---|---|---|
|RTA|G0/0|SW1|G0/1|
|RTA|G0/1|SW2|G0/1|
|SW1|F0/1|PC-1|Fastethernet0|
|SW2|F0/1|PC-2|Fastethernet0|

Change hostname, configure passwords (Ciscoenpa55 as encrypted password, Ciscolinepa55 as the password on the lines), configure message banner.

```
Router> enable
Router# conf t

Router(config)# hostname RTA

RTA(config)# enable secret Ciscoenpa55

RTA(config)# line console 0
RTA(config-line)# password Ciscolinepa55
RTA(config-line)# login
RTA(config-line)# exit

RTA(config)#line vty 0 4
RTA(config-line)# password Ciscolinepa55
RTA(config-line)# login
RTA(config-line)# exit

RTA(config)# service password-encryption 

RTA(config)# banner motd $The day banner$
```

Configure interface addressing, descriptions, save configurations.
```
RTA(config)#interface g0/0
RTA(config-if)#ip address 10.10.10.1 255.255.255.0
RTA(config-if)#description Link to SW1
RTA(config-if)#no shutdown
RTA(config-if)#exit

RTA(config)#interface g0/1
RTA(config-if)#ip address 10.10.20.1 255.255.255.0
RTA(config-if)#description Link to SW2
RTA(config-if)#no shutdown
RTA(config-if)#end

RTA#copy running-config startup-config
```

Configure SW1 and SW2.
```
Switch>enable
Switch#config terminal
Switch(config)#hostname SW1

SW1(config)#enable secret Ciscoenpa55

SW1(config)#line console 0
SW1(config-line)#password Ciscolinepa55
SW1(config-line)#login
SW1(config-line)#exit

SW1(config)#line vty 0 4
SW1(config-line)#password Ciscolinepa55
SW1(config-line)#login
SW1(config-line)#exit

SW1(config)#service password-encryption 

SW1(config)#interface vlan 1
SW1(config-if)#ip address 10.10.10.2 255.255.255.0
SW1(config-if)#no shutdown
SW1(config-if)#exit

SW1(config)#ip default-gateway 10.10.10.1
SW1(config)#end

SW1#copy running-config startup-config

Switch>enable
Switch#config terminal
Switch(config)#hostname SW2

SW2(config)#enable secret Ciscoenpa55

SW2(config)#line console 0
SW2(config-line)#password Ciscolinepa55
SW2(config-line)#login
SW2(config-line)#exit

SW2(config)#line vty 0 4
SW2(config-line)#password Ciscolinepa55
SW2(config-line)#login
SW2(config-line)#exit

SW2(config)#service password-encryption 

SW2(config)#interface vlan 1
SW2(config-if)#ip address 10.10.20.2 255.255.255.0
SW2(config-if)#no shutdown
SW2(config-if)#exit

SW2(config)#ip default-gateway 10.10.20.1
SW2(config)#end

SW2#copy running-config startup-config
```

For PC-1 and PC-2, fill in ip addresses, subnet masks, configure default gateway to RTA.