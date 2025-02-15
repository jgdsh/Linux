# Aruba Switch Configuration & Commands

> [Commands switch Reference Guide](https://arubanetworking.hpe.com/techdocs/CLI-Bank/Content/Home.htm)

## Show commands

- Shows information about the status of the role applied on ports

  `switch# show aaa authentication port-access interface all`

- Shows detailed active port access clients information including the VLAN group and VLAN association for each of the authenticated clients. The output can be filtered by interface or MAC address

  `switch# show port-access clients interface 1/1/7-1/1/8 detail`

- Showing information for a particular client MAC address:

  `switch# show port-access clients mac 2c:41:38:7f:35:c8 detail`

- Shows a summary of the IPv4 and IPv6 neighbor entries on the switch for all VRFs or a specific VRF

  `switch# show arp summary all-vrfs`