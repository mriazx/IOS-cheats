## Switch Configuration
The switch comes preconfigured and only needs to be assigned basic security information before being connected to the network. Elements that are usually configured on a LAN switch include: host name, management IP address information, passwords, and descriptive information.

Before configuring a switch, review the following initial switch configuration tasks:

### Configure the device name.

```console
Switch> enale
Switch# configure terminal
Switch(config)# hostname <name>
```

### Secure user EXEC mode.

```console
Switch(config)# enable secret class
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

### Secure privileged EXEC mode.

```console
Switch(config)# enable secret password
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
  
