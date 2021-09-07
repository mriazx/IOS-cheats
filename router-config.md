## Router Configuration
The following tasks should be completed when configuring initial settings on a router.

### Configure the device name.

```console
Router> enale
Router# configure terminal
Router(config)# hostname <name>
```

### Secure privileged EXEC mode.

```console
Router(config)# enable secret <password>
```

### Secure user EXEC mode.

```console
Router(config)# line console 0
Router(config-line)# password <password>
Router(config-line)# login
Router(config-line)# exit
```

### Secure remote Telnet / SSH access.

```console
Router(config)# line vty 0 15
Router(config-line)# password <password>
Router(config-line)# login
Router(config-line)# transport input ssh telnet
Router(config-line)# exit
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
  
