Which command will display the current contents of non-volatile random-access memory (NVRAM)?  
`show startup-configuration`  

**Secure access to the console line**  
```
S1(config)# line console 0
S1(config-line)# password letmein
S1(config-line)# login
S1(config-line)# exit
```

Why is the login command required?  
In order for the password checking process to work, it requires both the login and password commands 

**Secure access to priviledge EXEC mode**  
```
S1(config)# enable secret itsasecret
```
The enable password should be replaced with the newer encrypted secret password using the enable secret command. Set the enable secret password to itsasecret. The enable secret password overrides the enable password. If both are configured on the switch, you must enter the enable secret password to enter privileged EXEC mode.

**configure switch with ip address**
```
S2(config)#interface vlan 1
S2(config-if)#ip address 192.168.1.254 255.255.255.0
S2(config-if)#no shutdown
```

