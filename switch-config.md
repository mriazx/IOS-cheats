## Switch Configuration
The switch comes preconfigured and only needs to be assigned basic security information before being connected to the network. Elements that are usually configured on a LAN switch include: host name, management IP address information, passwords, and descriptive information.

Before configuring a switch, review the following initial switch configuration tasks:

### Configure the device name.

```console
Switch> enable
Switch# configure terminal
Switch(config)# hostname <name>
```

### Secure privileged EXEC mode.

```console
Switch(config)# enable secret <password>
```

### Secure user EXEC mode.

```console
Switch(config)# line console 0
Switch(config-line)# password <password>
Switch(config-line)# login
```

### Secure remote Telnet / SSH access.

```console
Switch(config-line)# line vty 0 15
Switch(config-line)# password <password>
Switch(config-line)# login
Switch(config-line)# exit
```


### Secure all passwords in the config file.

```console
Switch(config)# service password-encryption
```

### Provide legal notification.

```console
Switch(config)# banner motd <delimiter message delimiter>
```

### Configure the management SVI.
  
```console
Switch(config)# interface vlan 1
Switch(config-if)# ip address <ip-address> <subnet-mask>
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)# ip default-gateway <gateway ip-address>
Switch(config)# end
```

### Save the configuration.
  
```console
Switch# copy running-config startup-config
```
## Secure Remote Access

### Verify that the passwords are set correctly. 

```console
Switch# show running-config command.
```

## Configure SSH

### Verify SSH support.

```console
Switch# show ip ssh
```
### Configure the IP domain.

```console
Switch(config)# ip domain-name <domain name>
```
### Generate RSA key pairs.

```console
Switch(config)# crypto key generate rsa
The name for the keys will be: Switch.<domain name>
...
How many bits in the modulus [512]:1024
...  
```

### Configure user authentication.

```console
Switch(config)#username <name> secret <password>
```

### Configure the vty lines.

To configure all vty lines ranging from 0 to 15

```console
Switch(config)#line vty 0 15
Switch(config-line)#transport input ssh
Switch(config-line)#login local
Switch(config-line)#exit
```

### Configure Switch to use SSH 2.0.

```console
Switch(config)#ip ssh version 2
```

**Note:** To delete the RSA key pair, use the `crypto key zeroize rsa` global configuration mode command. After the RSA key pair is deleted, the SSH server is automatically disabled.
