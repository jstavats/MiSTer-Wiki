# Network access

MiSTer board can be access through on-board Ethernet port. System has **FTP**, **SSH**, **SFTP** services running.

User name: **root**  Password: **1**

By default, DHCP is used to acquire an IP address for the board.
You can find it from your router (easier way), or from console connected to the board using the command **ifconfig**

The default MAC address for the on-board Ethernet port is `02:03:04:05:06:07`. Please consider this when connecting more than one MiSTer board via the on-board Ethernet port to your network.

> TODO: How to setup a custom MAC address.

## Setting up a static IP address

Currently the best way to do this is using `connmanctl` (try `connmanctl help` for more info).
* Create /var/lib/connman directory so changes will persist across reboots
```
# mkdir /var/lib/connman
```
* Find your on-board network service name.
```
# connmanctl services
*AO Wired                ethernet_020304050607_cable
```
* Setup IP address (e.g. `192.168.1.123`, should be unused), subnet mask (e.g. `255.255.255.0`) and gateway (e.g. `192.168.1.1`, typically your router IP address). To configure the right device use the service name returned from above command (e.g. `ethernet_020304050607_cable`). This will disable the use of DHCP.
```
# connmanctl config ethernet_020304050607_cable --ipv4 manual 192.168.1.123 255.255.255.0 192.168.1.1
```
* Setup one or more DNS server(s) (e.g. `192.168.1.1` from your router, `8.8.8.8` from Google DNS.
```
# connmanctl config ethernet_020304050607_cable --nameservers 192.168.1.1 8.8.8.8
```

You can write a script to help with typing and remembering your settings.

> You can also setup your on-board network connection by editing `/etc/network/interfaces`. This is currently not advised. Because if you have a DHCP server in your network, the network stack will still contact the DHCP server and assign the returned IP address regardless, leading to usually unwanted behavior.

## (Re)Enabling DHCP

```
# connmanctl config ethernet_020304050607_cable --dhcp
```

## Other

**mc** (midnight commander) file manager is available for easier folder navigation.

The root of SD card: **/media/fat**

Related: [Serial Console Access](Console-connection)
