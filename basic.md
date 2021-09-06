# IOS Commands
As a security feature, the Cisco IOS software separates management access into the following two command modes:

**User EXEC Mode:** This mode has limited capabilities but is useful for basic operations. It allows only a limited number of basic monitoring commands but does not allow the execution of any commands that might change the configuration of the device. The user EXEC mode is identified by the CLI prompt that ends with the > symbol.

**Privileged EXEC Mode:** To execute configuration commands, a network administrator must access privileged EXEC mode. Higher configuration modes, like global configuration mode, can only be reached from privileged EXEC mode. The privileged EXEC mode can be identified by the prompt ending with the # symbol.

## Navigation
Enter privileged EXEC mode using the `enable` command.
```console
Switch> enable
```
Return to user EXEC mode using the `disable` command.
```console
Switch# disable
```
Re-enter privileged EXEC mode.
```console
Switch> enable
```
Enter global configuration mode using the `configure terminal` command.
```console
Switch# configure terminal
```
Exit global configuration mode and return to privileged EXEC mode using the `exit` command.
```console
Switch(config)# exit
```
Re-enter global configuration mode.
```console
Switch# configure terminal
```
Enter line subconfiguration mode for the console port using the `line console 0` command.
```console
Switch(config)# line console 0
```
Return to global configuration mode using the `exit` command.
```console
Switch(config-line)# exit
```
Enter VTY line subconfiguration mode using the `line vty 0 15` command.
```console
Switch(config)# line vty 0 15
```
Return to global configuration mode.
```console
Switch(config-line)# exit
```
Enter the VLAN 1 interface subconfiguration mode using the `interface vlan 1` command.
```console
Switch(config)# interface vlan 1
```
From interface configuration mode, switch to line console subconfiguration mode using the `line console 0` global configuration command.
```console
Switch(config-if)# line console 0
```
Return to privileged EXEC mode using the `end` command.
```console
Switch(config-line)# end
```
| Command | Used to |
|---------|---------|
|`show running-config`|Verifies the current configuration and settings.|
|`show interfaces`|Verifies the interface status and displays any error messages.|
|`show ip interface`|Verifies the Layer 3 information of an interface.|
|`show arp`|Verifies the list of known hosts on the local Ethernet LAN.|
|`show ip route`|Verifies the Layer 3 routing information.|
|`show protocols`|Verifies which protocols are operational.|
|`show version`|Verifies the memory, interfaces, and licenses of the device.|


