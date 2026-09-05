# DHCP, DNS & Network Services Lab

## Overview

This lab was built in Cisco Packet Tracer to practice configuring centralized network services across multiple VLANs.

I created four VLANs for separate departments, configured router-on-a-stick for inter-VLAN routing, and used a centralized server to provide DHCP, DNS, and HTTP services.

Because the DHCP server was located in a different VLAN from the client devices, I configured DHCP relay using `ip helper-address` to allow DHCP requests to reach the server across subnet boundaries.

## Lab Objectives

- Create and configure four VLANs
- Configure access ports for each VLAN
- Configure an 802.1Q trunk between the switch and router
- Configure router-on-a-stick for inter-VLAN routing
- Configure centralized DHCP pools
- Configure DHCP relay with `ip helper-address`
- Configure DNS name resolution
- Configure and test an HTTP web service
- Verify connectivity and troubleshoot configuration issues
## Network Design

| VLAN | Department | Network | Default Gateway | Devices |
|---|---|---|---|---|
| 10 | ADMIN | 192.168.10.0/24 | 192.168.10.1 | PC0, PC1 |
| 20 | SALES | 192.168.20.0/24 | 192.168.20.1 | PC2, PC3 |
| 30 | IT | 192.168.30.0/24 | 192.168.30.1 | PC4, PC5 |
| 40 | SERVERS | 192.168.40.0/24 | 192.168.40.1 | Server0 |

### Server Configuration

| Service | Configuration |
|---|---|
| Server IP | 192.168.40.10/24 |
| Default Gateway | 192.168.40.1 |
| DHCP | Centralized DHCP server for VLANs 10, 20, and 30 |
| DNS | 192.168.40.10 |
| DNS A Record | intranet.atlas.local → 192.168.40.10 |
| HTTP | Internal web service |
## Network Topology

The network uses four VLANs connected through a Cisco 2960 switch. A Cisco 2911 router provides inter-VLAN routing using router-on-a-stick. The switch-to-router connection is configured as an 802.1Q trunk.

![Lab 02 Network Topology](lab02-network-topology.png)
