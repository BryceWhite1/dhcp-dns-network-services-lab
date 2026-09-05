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
