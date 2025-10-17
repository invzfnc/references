ssh (Secure Shell)
Cryptographic network protocol, establish secure and encrypted connections. In context of Linux, SSH is the primary method for remote administration, allowing users to connect to and manage Linux servers from a local machine.

```sh
ssh user@server -p port
```
`user`: username
`server`: server ip address or domain name
`port`: port number. standard port for ssh is 22

Example
```sh
ssh ctf-player@titan.picoctf.net -p 58833
```