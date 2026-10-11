# TechNova Ltd. Network Implementation Using Cisco Packet Tracer

This project demonstrates the design and configuration of a departmental network for **TechNova Ltd.** using Cisco Packet Tracer. It implements DHCP for automatic IP addressing and an Access Control List (ACL) to restrict ICMP traffic from the Sales network to the IT network while allowing authorised HTTP access to the IT server.

## Table of Contents

- Project Overview
- Network Topology
- Tools and Technologies
- Configuration Steps
- Results and Findings
- Author

## Project Overview

The purpose of this project was to design, implement, and test a network infrastructure for TechNova Ltd., comprising three departments: IT, Sales, and HR.

The project objectives were to:

- Create separate IP networks for the IT, Sales, and HR departments.
- Configure a router to facilitate communication between departmental networks.
- Configure the IT server as a DHCP server to provide automatic IP addressing and other network configuration information.
- Implement an ACL to restrict ICMP traffic from Sales to IT in accordance with the company's network security policy.
- Verify that authorised network services, including HTTP access to the IT server, remain available.
- Test network connectivity and validate the effectiveness of the access control policy.

## Network Topology

The network consists of three departmental networks connected through a router.

### Departmental Network Layout

- **IT Department:** Two PCs, one switch, and one server configured as the DHCP server and providing HTTP service.
- **Sales Department:** Two PCs and one switch.
- **HR Department:** Two PCs and one switch.
- **Router:** Connects the three departmental networks and facilitates inter-network communication.
- **DHCP Server:** Provides automatic IP addresses, subnet masks, default gateways, and DNS server information to departmental PCs.

### IP Addressing Scheme

| Department | Network Address   | Subnet Mask     |
| ---------- | ----------------- | --------------- |
| IT         | `192.168.10.0/24` | `255.255.255.0` |
| Sales      | `192.168.20.0/24` | `255.255.255.0` |
| HR         | `192.168.30.0/24` | `255.255.255.0` |

The DHCP server assigns IP configurations appropriate to each department's network.

**Note:** The individual PC addresses, router interface addresses, and server address are not specified in the project description. Refer to the Packet Tracer configuration for the exact assignments.

### Network Security Policy

- **HR to IT:** ICMP connectivity is permitted, as demonstrated by a successful ping test.
- **Sales to IT:** ICMP traffic is restricted by an ACL.
- **Sales to IT server:** HTTP access is permitted, allowing Sales PCs to access the server's HTTP service despite the ICMP restriction.

## Tools and Technologies

- **Cisco Packet Tracer:** Network design, configuration, and simulation.
- **Cisco Router:** Interconnects departmental networks and applies access control policies.
- **Ethernet Switches:** Connect PCs and the server within departmental networks.
- **DHCP:** Provides automatic IP addressing and network configuration information.
- **Access Control Lists (ACLs):** Control network traffic according to the security policy.
- **Internet Control Message Protocol (ICMP):** Used to test network connectivity with ping.
- **HTTP:** Provides access to the IT server's web service.
- **Command-Line Interface (CLI):** Used to configure the router and ACL rules.

## Configuration Steps

1. **Build the network topology.**
   - Create the IT, Sales, and HR departmental networks in Cisco Packet Tracer.
   - Connect two PCs and a switch in each department.
   - Add a server and connect it to the IT network.
   - Connect the departmental switches to a router.
2. **Configure IP addressing.**
   - Assign the IT department to `192.168.10.0/24`.
   - Assign the Sales department to `192.168.20.0/24`.
   - Assign the HR department to `192.168.30.0/24`.
   - Configure the appropriate router interfaces and default gateways.
3. **Configure the DHCP server.**
   - Configure the IT server to provide DHCP services.
   - Create address pools for the departmental networks.
   - Specify the appropriate subnet masks, default gateways, and DNS server information.
   - Configure DHCP relay on the router interfaces for remote departmental networks, where required.
4. **Configure the departmental PCs.**
   - Set each PC to obtain its IP configuration automatically through DHCP.
   - Verify that each PC receives an IP address, subnet mask, default gateway, and DNS server information appropriate to its network.
5. **Configure the HTTP service.**
   - Enable the HTTP service on the IT server.
   - Verify that the server is reachable using its assigned IP address and that the HTTP service is available.
6. **Configure the router ACL.**
   - Access the router CLI.
   - Create and apply an ACL to restrict ICMP traffic originating from the Sales network and destined for the IT network.
   - Ensure other authorised traffic, including HTTP, is permitted in accordance with the network security policy.
   - Apply the ACL to the appropriate router interface and direction.
   **Security objective:** Restrict Sales-to-IT ping traffic without preventing authorised HTTP access to the IT server.

   *The exact router commands and ACL number are not reproduced here because the complete command text is not available in the extracted project description.*
7. **Test HR-to-IT connectivity.**
   - Open the command prompt on an HR PC.
   - Ping a PC in the IT department using its assigned IP address.
   - Confirm that the ping succeeds.
8. **Test Sales-to-IT ICMP restrictions.**
   - Open the command prompt on a Sales PC.
   - Ping a PC in the IT department.
   - Confirm that the ping fails in accordance with the configured ACL.
9. **Test Sales-to-IT HTTP access.**
   - Open the web browser on a Sales PC.
   - Enter the IP address of the IT server.
   - Verify that the server's HTTP service is accessible despite the ICMP restriction.
10. **Document the results.**
    - Capture the DHCP configuration details.
    - Record the successful HR-to-IT ping.
    - Record the failed Sales-to-IT ping.
    - Document the ACL configuration and successful HTTP access from Sales to the IT server.

## Results and Findings

The network was configured and tested against the intended connectivity and security requirements.

### 1. Successful DHCP Configuration

The departmental PCs successfully received their IP addresses, subnet masks, default gateways, and DNS server information from the DHCP server. Each PC received an IP configuration appropriate to its departmental network.

**Finding:** DHCP successfully provided automatic network configuration to the PCs.

### 2. Successful HR-to-IT Connectivity

A ping test from an HR PC to an IT PC was successful. Four ICMP packets were sent, and all four were received, resulting in **0% packet loss**.

**Finding:** Communication between the HR and IT networks was functioning correctly for the tested ICMP traffic.

### 3. Restricted Sales-to-IT ICMP Traffic

A ping test from a Sales PC to an IT PC failed. All four ICMP packets were unsuccessful, resulting in **100% packet loss** and a `Destination Host Unreachable` message.

**Finding:** The observed result was consistent with the intended restriction on ICMP traffic from Sales to IT.

### 4. Successful Sales-to-IT HTTP Access

Sales PCs successfully accessed the HTTP service provided by the IT server.

**Finding:** HTTP traffic remained permitted between Sales and the IT server while ICMP traffic from Sales to IT remained restricted.

### 5. Overall Security Outcome

The project demonstrated how network segmentation, DHCP, routing, and ACLs can be combined to implement departmental network policies.

The tests confirmed the intended behaviour for the scenarios examined:

- Automatic IP configuration was successful.
- HR-to-IT ICMP connectivity was successful.
- Sales-to-IT ICMP connectivity was restricted.
- Sales-to-IT HTTP access was successful.

These results demonstrate **protocol-specific traffic control**: restricting ping traffic does not necessarily prevent access to other authorised services.

## Author

**Sunday Tanimowo**

- **Project:** TechNova Ltd. Network Implementation Using Cisco Packet Tracer
- **Student ID:** CS-C26-09-NA-006
- **Date:** 6 October 2026

This project was completed as part of my practical development in network configuration, access control, and cybersecurity fundamentals.
