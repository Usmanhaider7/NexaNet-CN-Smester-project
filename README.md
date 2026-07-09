# Enterprise Network Design with Inter-VLAN Routing

## Project Overview
This project is a Cisco Packet Tracer simulation of an enterprise network topology. It demonstrates the implementation of **Router-on-a-Stick** for inter-VLAN routing, allowing logical segmentation of departments while maintaining cross-departmental communication and centralized DHCP services.

## Network Topology
The network consists of:
*   **1x Cisco 2911 Router** acting as the default gateway and DHCP server for all VLANs.
*   **1x Cisco 3560 Core Switch** acting as the central distribution layer.
*   **5x Cisco 2960 Access Switches** connecting end devices.
*   **End Devices:** 9 PCs and a Server Farm (DNS, Web, DHCP).

*(Include your topology screenshot here, e.g., `![Topology](topology.png)`)*
![Network Topology](Screenshot%202026-07-10%20021053.png)

## VLAN and IP Addressing Scheme

| VLAN ID | Department Name | Network Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **VLAN 10** | HR | 192.168.10.0 | 255.255.255.0 | 192.168.10.1 |
| **VLAN 20** | IT | 192.168.20.0 | 255.255.255.0 | 192.168.20.1 |
| **VLAN 30** | Finance | 192.168.30.0 | 255.255.255.0 | 192.168.30.1 |
| **VLAN 40** | Sales | 192.168.40.0 | 255.255.255.0 | 192.168.40.1 |
| **VLAN 50** | Management | 192.168.50.0 | 255.255.255.0 | 192.168.50.1 |

## Core Technologies Implemented
*   **802.1Q Trunking:** Configured between the Core Switch and all Access Switches, as well as the Core Switch and the Router.
*   **Inter-VLAN Routing:** Achieved using sub-interfaces on the Cisco 2911 router (`Gig0/0.10`, `Gig0/0.20`, etc.).
*   **DHCP Pools:** The central router dynamically assigns IP addresses to end devices based on their respective VLANs.
*   **Spanning Tree Protocol (STP):** PortFast is enabled on access ports to reduce convergence time for end-users.

## How to Run This Project
1. Download the `.pkt` file from this repository.
2. Open it using **Cisco Packet Tracer**.
3. Allow 30-60 seconds for the switches to complete Spanning Tree convergence (or click Fast Forward Time).
4. Open the Command Prompt on any PC (e.g., `192.168.10.11`) and ping the Web Server (`192.168.50.3`) to verify inter-VLAN routing.

## Author
[Your Name] - Computer Networks Semester Project
