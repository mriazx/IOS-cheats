## Allocating Static IP Addresses with DHCP
Ensure that router assigns the same IP address to a particular device every time it connects.

```shell
Router1#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
Router1(config)#ip dhcp pool IAN
Router1(dhcp-config)#host 172.25.1.33 255.255.255.0
Router1(dhcp-config)#client-identifier 0100.0103.85e9.87
Router1(dhcp-config)#client-name win2k
Router1(dhcp-config)#default-router 172.25.1.1 
Router1(dhcp-config)#domain-name oreilly.com
Router1(dhcp-config)#dns-server 172.25.1.1 
Router1(dhcp-config)#exit
Router1(config)#end
Router1#
```

