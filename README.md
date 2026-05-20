# Cisco 1800 Router + Catalyst 2950 Switch Homelab

## Overview

This project is a beginner CCNA homelab where I connected a Cisco 1800 router to a Catalyst 2950 switch and configured basic networking services.

The goal of this lab was to practice:
- Basic Cisco CLI navigation
- Hostname configuration
- Securing devices with type 9 scrypt encryption
- Interface configuration
- DHCP configuration
- End device connectivity

---

# Network Topology

Router -> Switch -> Laptop

---

# Devices Used

- Cisco 1800 Router
- Cisco Catalyst 2950 Switch
- Laptop/PC
- Ethernet cables

---

# Configurations Completed

## Router
- Configured hostname
- Configured enable algorithm-type scrypt secret <password>
- Configured FastEthernet interface
- Configured DHCP pool
- Assigned gateway address

## Switch
- Configured hostname
- Configured enable algorithm-type scrypt secret <password>
- Configured switch ports

## End Device
- Configured laptop to obtain IP automatically using DHCP
- Verified connctivity

---

# Router Configuration

```cisco
hostname R1

enable secret class

interface FastEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown

ip dhcp pool LAN
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 8.8.8.8
```

---

# Switch Configuration

```cisco
hostname SW1

enable secret class

interface FastEthernet0/1
 switchport mode access
 no shutdown
```

---

# Verification

## DHCP Success
The laptop successfully received an local IP adress from the router DHCP server.

Example:
- IP Address: 192.168.1.x
- Default Gateway: 192.168.1.1

---

# What I Learned

- How routers and switches connect in a LAN
- Basic Cisco CLI commands
- Interface configuration
- DHCP setup and deployment
- Basic network troubleshooting

---

# Future Improvements

- Configure SSH
- Add VLANs (already about to)
- Configure trunk ports
- Add multiple PCs 
- Configure static routing
- Practice ACLs
- Add a WAP
