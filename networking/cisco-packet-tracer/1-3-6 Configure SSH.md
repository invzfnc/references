Why SSH over Telnet? Telnet uses insecure plain text communication, SSH provides security for remote connections by providing strong encryption of all transmitted data between devices.

**remotely access switch**  
`C:\>telnet 10.10.10.2` - switch ip  
From EXEC, go into privileged EXEC with `enable`  

**save/backup current configuration**  
that way can just revert back to config by toggling power of switch  
`S1#copy running-config startup-config` then enter

**password encryption**  
`S1(config)# **service password-encryption**`  
`show run` to verify passwords are encrypted

**configure domain name**  
`S1(config)#ip domain-name netacad.pka`

**keygen**  
`S1(config)# crypto key generate rsa` then `1024` - secure keys are needed to encrypt the data, generate the RSA keys using a 1024 key length

**create ssh user, reconfigure vty lines for ssh-only access**  
`S1(config)# username administrator secret cisco` - create an user with name administrator with the password cisco  
`S1(config)# line vty 0 15` - change parameters for remote access  
`S1(config-line)# transport input ssh` - only allow ssh for remote management  
`S1(config-line)# login local` - select to authenticate against usernames in this device  
`S1(config-line)# no password cisco` - remove the existing vty line password?

**verify ssh implementation**  
`C:\>telnet 10.10.10.2` - this should fail as intended  
`C:\>ssh -l administrator 10.10.10.2` - `ssh` to see usage instructions (`ssh -l username target)