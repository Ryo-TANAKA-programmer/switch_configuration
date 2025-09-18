## Switch Configuration
### This is a documentation for Cisco switch/router configuration.

### Enable Secret

a password or secret stored as a hash using the Cisco Type 9 encryption algorithm, which is based on the Scrypt hashing algorithm and is designed to be computationally expensive to crack. Passwords configured with the Type 9 algorithm will begin with "\(9\)". 

```
username cisco algorithm-type scrypt secret ccna
enable algorithm-type scrypt secret ccna

enable secret 9 $9$J19FIAftPZf7c3$l3koe1VkzliJg5KQU.JgBhXj4RzTxEUDZnF2s1b.Hn6
username cisco secret 9 $9$J19FIAftPZf7c3$Mux3wTz1Kth/NxeyEk.E8.QBckaZchVfllsGnxO8/0A
```

### console/SSH/Telnet

`logging synchronous` prevents system and debug messages from being interspersed with your input on the console or VTY lines by redisplaying your typed command on a new line after an interrupting message occurs.

```
line console 0
  logging synchronous
```

### Layer 2 switch to a Management VLAN with an IP

If your switch is a pure Layer 2 switch (not capable of routing), it needs a default gateway to allow it to send management traffic (like Telnet or SSH) to a remote network. 

```
ip default-gateway
```

