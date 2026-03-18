`Switch# configure terminal` - enter configuration mode  
`Switch(config-if)#` - switch management interface configuration  

`Switch# configure terminal` - enter global configuration mode  
`Switch(config)# interface vlan 1` - create a virtual host on the switch  
`Switch(config-if)# no shutdown` - turn on the virtual interface  

`Switch# show version` - like --version  

`Switch# show interface gig1/0/6` - examine default properties of the GigabitEthernet 1/0/6 interface used by PC-A, see 1.1.7  

**basic switch config**  
`Switch(config)# hostname S1` - change hostname to S1  
`S1(config)# no ip domain-lookup` - suppress DNS attempt when a command is mistyped  
`S1(config)# service password-encryption` - encrypt all passwords - except secret  
`S1(config)# enable secret password` - must have an enable password for remote config  
`S1(config)# banner motd #(start typing message)#` - display message when logging in  

**change the vlan management to vlan other than vlan 1**  
`S1(config)# vlan 99` - create VLAN 99 in the VLAN.DAT database  
`S1(config-vlan)# exit`  
`S1(config)# interface vlan 99` - create a virtual host on the switch  
`S1(config)# ip address 192.168.1.2 255.255.255.0` - set ip address of the switch to 192.168.1.2, with a subnet mask of 255.255.255.0 on the internal virtual interface VLAN 99

**assign all user ports to vlan 99**  
`S1(config)# **interface range gig1/0/1-24**` - select a range of ports to be configured the same  
`S1(config-if-range)# **switchport access vlan 99**` - assign this port(s) to vlan 99  
`S1# show vlan brief` - to verify all ports are in vlan 99  

**config default gateway for S1**  
`S1(config)# ip default-gateway 192.168.1.1` - assuming that the LAN interface on the router is 192.168.1.1, set the default gateway for the switch  

**set password for console port access**  
`S1(config)# line console 0` - enter the console connection configuration mode  
`S1(config-line)# logging synchronous` - assists by keeping command entry more orderly. to prevent console messages from interrupting commands  
`S1(config-line)# password cisco` - set user level password to cisco  
`S1(config-line)# login` - instruct the router that you want it to check for a password  
`S1(config-line)# exit`  

**configure the virtual terminal (vty) lines to allow Telnet access**  
`S1(config)# line vty 0 15`  
`S1(config-line)# password cisco`  
`S1(config-line)# login`  
`S1(config-line)# end`  

**verify and test network connectivity**  
`S1# show run` - display switch configuration  
`S1# show interface vlan 99` - display vlan 99 configuration  

**test end-to-end connectivity with ping**  
`C:\> ping 192.168.1.2`  
`C:\> ping 2001:db8:acad:1::2`  

**test remote management with telnet**  
Desktop > Telnet/SSH Client > Dropdown choose Telnet, enter IP (192.168.1.2 in this case)