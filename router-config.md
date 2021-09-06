## Router Configuration
The Router comes preconfigured and only needs to be assigned basic security information before being connected to the network. Elements that are usually configured on a LAN switch include: host name, management IP address information, passwords, and descriptive information.

Before configuring a switch, review the following initial switch configuration tasks:

### Configure the device name.

```console
Router> enale
Router# configure terminal
Router(config)# hostname <name>
```

### Secure user EXEC mode.

```console
Router(config)# enable secret class
Router(config)# line console 0
Router(config-line)# password <password>
Router(config-line)# login
```

### Secure remote Telnet / SSH access.

```console
Router(config-line)# line vty 0 15
Router(config-line)# password <password>
Router(config-line)# login
Router(config-line)# exit
```

### Secure privileged EXEC mode.

```console
Router(config)# enable secret password
```

### Secure all passwords in the config file.

```console
Router(config)# service password-encryption
```

### Provide legal notification.

```console
Router(config)# banner motd <delimiter message delimiter>
```

### Save the configuration.
  
```console
Router# copy running-config startup-config
```
  
