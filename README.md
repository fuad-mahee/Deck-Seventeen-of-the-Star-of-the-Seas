# Deck Seventeen of the Star of the Seas - Network Design Project

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?style=flat&logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![Project Status](https://img.shields.io/badge/Status-Complete-success)](https://github.com)

## 📋 Project Overview

This project presents a comprehensive network infrastructure design for **Deck Seventeen of the Star of the Seas** cruise ship. The implementation demonstrates enterprise-level network architecture using Cisco Packet Tracer, incorporating advanced networking concepts including VLSM (Variable Length Subnet Masking), VLANs, routing protocols, and network segmentation.

### Course Information
- **Course Code**: CSE421
- **Project Type**: Network Design and Implementation
- **Group Number**: Group 908
- **Platform**: Cisco Packet Tracer

## 🎯 Project Objectives

- Design and implement a scalable network infrastructure for a cruise ship deck
- Apply VLSM techniques for efficient IP address allocation
- Configure VLANs for network segmentation and security
- Implement inter-VLAN routing and network connectivity
- Demonstrate practical application of networking concepts in real-world scenarios
- Ensure high availability and redundancy in the network design

## 📁 Project Structure

```
Deck-Seventeen-of-the-Star-of-the-Seas/
│
├── Group908.pkt                                    # Main Packet Tracer simulation file
├── Group_908_topology.png                          # Network topology diagram
├── Group908_VLSM Tree + Address Table + 
│   Configuration Commands + Assumptions.pdf        # Technical documentation
├── Group908_Member contribution.pdf                # Team member contributions
├── Deck Seventeen of the Star of the Seas.pdf     # Complete project report
├── .gitattributes                                  # Git configuration
└── README.md                                       # This file
```

## 🔧 Technical Specifications

### Network Design Components

- **VLSM Implementation**: Optimized IP address allocation using Variable Length Subnet Masking
- **VLAN Configuration**: Logical network segmentation for different departments/areas
- **Routing Protocols**: Dynamic routing configuration for scalable network operations
- **Network Devices**: Routers, switches, and end devices configured for enterprise operations
- **Security Measures**: Access control and network segmentation strategies

### Documentation Included

1. **VLSM Tree**: Hierarchical subnet breakdown and IP address allocation
2. **Address Table**: Comprehensive listing of all network addresses and assignments
3. **Configuration Commands**: Complete device configuration scripts and commands
4. **Network Assumptions**: Design constraints and assumptions made during implementation
5. **Topology Diagram**: Visual representation of the network architecture

## 🚀 Getting Started

### Prerequisites

- **Cisco Packet Tracer** (Version 7.3 or later recommended)
  - Download from: [Cisco Networking Academy](https://www.netacad.com/courses/packet-tracer)
- Basic understanding of networking concepts
- Familiarity with Cisco IOS commands

### Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Deck-Seventeen-of-the-Star-of-the-Seas
   ```

2. **Open the Packet Tracer file**
   - Launch Cisco Packet Tracer
   - Open `Group908.pkt` file
   - Wait for the simulation to load completely

3. **Review Documentation**
   - Refer to `Deck Seventeen of the Star of the Seas.pdf` for complete project details
   - Check `Group908_VLSM Tree + Address Table + Configuration Commands + Assumptions.pdf` for technical specifications

## 📖 How to Use

### Exploring the Network

1. **View Topology**: 
   - Open the `.pkt` file in Packet Tracer
   - Use the navigation tools to explore different areas of the network
   - Refer to `Group_908_topology.png` for an overview

2. **Inspect Configurations**:
   - Click on any device to view its configuration
   - Use CLI (Command Line Interface) to execute commands
   - Review running configurations using `show running-config`

3. **Test Connectivity**:
   - Use `ping` command to test connectivity between devices
   - Verify routing tables using `show ip route`
   - Check VLAN configurations with `show vlan brief`

4. **Simulation Mode**:
   - Switch to Simulation mode to observe packet flow
   - Add filters for specific protocols (ICMP, HTTP, etc.)
   - Analyze packet forwarding and routing decisions

## 🌐 Network Architecture

### Key Features

- **Hierarchical Design**: Three-tier architecture (Core, Distribution, Access)
- **Redundancy**: Multiple paths for critical network segments
- **Scalability**: Design supports future expansion and growth
- **Segmentation**: Logical separation of different functional areas
- **Efficiency**: Optimized IP address usage through VLSM

### Network Segments

The network is divided into multiple VLANs representing different functional areas of Deck Seventeen:

- Guest Services
- Entertainment Systems
- Security & Monitoring
- Staff Operations
- Management Network
- IoT Devices & Sensors

*(Refer to the technical documentation for specific VLAN IDs and IP ranges)*

## 🔢 VLSM Addressing Scheme

### Primary Network Blocks (192.168.0.0/16)

#### BLOCK A: COASTAL KITCHEN (192.168.10.0/24)

| Subnet | Purpose | Network Address | CIDR | Subnet Mask | IP Range | Usable Hosts |
|--------|---------|-----------------|------|-------------|----------|--------------|
| 1 | Kitchen Clients (Tables & Front Desk) | 192.168.10.0 | /28 | 255.255.255.240 | .1 to .14 | 14 |
| 2 | Kitchen Isolated Servers | 192.168.10.16 | /29 | 255.255.255.248 | .17 to .22 | 6 |

**VLSM Tree - Block A:**
```
192.168.10.0/24
│
├── Subnet 1: Kitchen Clients (Tables & Front Desk)
│   ├── Network: 192.168.10.0
│   ├── CIDR:    /28
│   ├── Mask:    255.255.255.240
│   └── Range:   .1 to .14 (14 Hosts)
│
└── Subnet 2: Kitchen Isolated Servers
    ├── Network: 192.168.10.16
    ├── CIDR:    /29
    ├── Mask:    255.255.255.248
    └── Range:   .17 to .22 (6 Hosts)
```

#### BLOCK B: GUEST SUITES (192.168.20.0/24)

| Subnet | Purpose | Network Address | CIDR | Subnet Mask | IP Range | Usable Hosts |
|--------|---------|-----------------|------|-------------|----------|--------------|
| 1 | Guest Tablets | 192.168.20.0 | /27 | 255.255.255.224 | .1 to .30 | 30 |

**VLSM Tree - Block B:**
```
192.168.20.0/24
│
└── Subnet 1: Guest Tablets
    ├── Network: 192.168.20.0
    ├── CIDR:    /27
    ├── Mask:    255.255.255.224
    └── Range:   .1 to .30 (30 Hosts)
```

#### BLOCK C: VENUES & ADMIN (192.168.30.0/24)

| Subnet | Purpose | Network Address | CIDR | Subnet Mask | IP Range | Usable Hosts |
|--------|---------|-----------------|------|-------------|----------|--------------|
| 1 | Venues (Pool, Bar, Sports) | 192.168.30.0 | /29 | 255.255.255.248 | .1 to .6 | 6 |
| 2 | Deck Manager (WS & DB) | 192.168.30.8 | /29 | 255.255.255.248 | .9 to .14 | 6 |

**VLSM Tree - Block C:**
```
192.168.30.0/24
│
├── Subnet 1: Venues (Pool, Bar, Sports)
│   ├── Network: 192.168.30.0
│   ├── CIDR:    /29
│   ├── Mask:    255.255.255.248
│   └── Range:   .1 to .6 (6 Hosts)
│
└── Subnet 2: Deck Manager (WS & DB)
    ├── Network: 192.168.30.8
    ├── CIDR:    /29
    ├── Mask:    255.255.255.248
    └── Range:   .9 to .14 (6 Hosts)
```

#### BLOCK D: CENTRAL CORE (192.168.100.0/24)

| Subnet | Purpose | Network Address | CIDR | Subnet Mask | IP Range | Usable Hosts |
|--------|---------|-----------------|------|-------------|----------|--------------|
| 1 | Central Servers (Web, DNS, Email) | 192.168.100.0 | /29 | 255.255.255.248 | .1 to .6 | 6 |

**VLSM Tree - Block D:**
```
192.168.100.0/24
│
└── Subnet 1: Central Servers (Web, DNS, Email)
    ├── Network: 192.168.100.0
    ├── CIDR:    /29
    ├── Mask:    255.255.255.248
    └── Range:   .1 to .6 (6 Hosts)
```

### Router-to-Router Links (10.0.0.0/8)

Point-to-point connections between routers using /30 subnets for optimal address utilization:

| Link | Connection | Network Address | CIDR | Subnet Mask | Assigned IPs |
|------|------------|-----------------|------|-------------|--------------|
| 1 | Deck 17 ↔ Kitchen Router | 10.0.0.0 | /30 | 255.255.255.252 | 10.0.0.1, 10.0.0.2 |
| 2 | Deck 17 ↔ Sub Router | 10.0.0.4 | /30 | 255.255.255.252 | 10.0.0.5, 10.0.0.6 |
| 3 | Deck 17 ↔ Central Router (Primary) | 10.0.0.8 | /30 | 255.255.255.252 | 10.0.0.9, 10.0.0.10 |
| 4 | Deck 17 ↔ Central Backup (Redundant) | 10.0.0.12 | /30 | 255.255.255.252 | 10.0.0.13, 10.0.0.14 |
| 5 | Central Router ↔ Server Router | 10.0.0.16 | /30 | 255.255.255.252 | 10.0.0.17, 10.0.0.18 |
| 6 | Central Backup ↔ Server Router | 10.0.0.20 | /30 | 255.255.255.252 | 10.0.0.21, 10.0.0.22 |

**VLSM Tree - Router Links:**
```
10.0.0.0/8
│
├── Link 1: Deck 17 -> Kitchen Router
│   ├── Network: 10.0.0.0
│   ├── CIDR:    /30 (255.255.255.252)
│   └── IPs:     .1 and .2
│
├── Link 2: Deck 17 -> Sub Router
│   ├── Network: 10.0.0.4
│   ├── CIDR:    /30 (255.255.255.252)
│   └── IPs:     .5 and .6
│
├── Link 3: Deck 17 -> Central Router (Primary)
│   ├── Network: 10.0.0.8
│   ├── CIDR:    /30 (255.255.255.252)
│   └── IPs:     .9 and .10
│
├── Link 4: Deck 17 -> Central Backup (Redundant)
│   ├── Network: 10.0.0.12
│   ├── CIDR:    /30 (255.255.255.252)
│   └── IPs:     .13 and .14
│
├── Link 5: Central Router -> Server Router
│   ├── Network: 10.0.0.16
│   ├── CIDR:    /30 (255.255.255.252)
│   └── IPs:     .17 and .18
│
└── Link 6: Central Backup -> Server Router
    ├── Network: 10.0.0.20
    ├── CIDR:    /30 (255.255.255.252)
    └── IPs:     .21 and .22
```

### VLSM Design Rationale

- **Efficient Address Utilization**: VLSM allows precise allocation based on actual host requirements
- **Scalability**: Reserved address space for future expansion in each block
- **/30 Subnets for P2P Links**: Minimizes IP waste on router-to-router connections (only 2 usable IPs needed)
- **Hierarchical Structure**: Clear separation between functional areas improves security and management
- **Redundancy**: Dual paths to central infrastructure ensure high availability

## 📊 Project Deliverables

| Deliverable | Description | File |
|------------|-------------|------|
| Network Simulation | Complete Packet Tracer implementation | `Group908.pkt` |
| Topology Diagram | Visual network architecture | `Group_908_topology.png` |
| Technical Documentation | VLSM, addressing, configurations | `Group908_VLSM Tree...pdf` |
| Project Report | Comprehensive project documentation | `Deck Seventeen of the Seas.pdf` |
| Member Contributions | Team member responsibilities | `Group908_Member contribution.pdf` |

## 👥 Team Contributions

Detailed information about individual team member contributions can be found in the `Group908_Member contribution.pdf` file.

## 🔍 Key Learning Outcomes

- **IP Addressing**: Mastery of VLSM and efficient IP allocation strategies
- **Network Segmentation**: Understanding VLAN implementation and benefits
- **Routing**: Configuration of static and dynamic routing protocols
- **Device Configuration**: Hands-on experience with Cisco IOS commands
- **Network Design**: Application of best practices in enterprise network architecture
- **Troubleshooting**: Problem-solving skills for network connectivity issues
- **Documentation**: Professional technical documentation practices

## 📝 Configuration Highlights

### Sample Commands (Examples)

```cisco
! VLAN Configuration
vlan 10
 name Guest-Services
vlan 20
 name Entertainment

! Interface Configuration
interface GigabitEthernet0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown

! Routing Configuration
router ospf 1
 network 192.168.0.0 0.0.255.255 area 0
```

*(For complete configuration commands, refer to the technical documentation)*

## 🛠️ Troubleshooting

### Common Issues

1. **Devices not connecting**:
   - Verify cable connections
   - Check interface status (`show ip interface brief`)
   - Ensure VLANs are properly configured

2. **Routing issues**:
   - Verify routing table (`show ip route`)
   - Check routing protocol configuration
   - Ensure proper network statements

3. **VLAN connectivity problems**:
   - Verify trunk configurations
   - Check VLAN assignments on access ports
   - Ensure inter-VLAN routing is configured

## 📚 Additional Resources

- [Cisco Packet Tracer Documentation](https://www.netacad.com/courses/packet-tracer)
- [Cisco IOS Command Reference](https://www.cisco.com/c/en/us/support/ios-nx-os-software/index.html)
- [VLSM Tutorial](https://www.cisco.com/c/en/us/support/docs/ip/routing-information-protocol-rip/13788-3.html)
- [VLAN Configuration Guide](https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst9300/software/release/16-12/configuration_guide/vlan/b_1612_vlan_9300_cg.html)

## 📄 License

This project is created for educational purposes as part of CSE421 coursework.

## 📞 Contact & Support

For questions or clarifications regarding this project, please refer to the project documentation or contact the team members listed in the contribution document.

---

**Note**: This project demonstrates theoretical network design and implementation. For production deployment, additional security measures, redundancy, and compliance requirements should be considered.

## 🎓 Acknowledgments

- Course Instructor and Teaching Assistants
- Cisco Networking Academy for Packet Tracer
- Team members for their collaborative effort

---

<div align="center">

**Star of the Seas - Deck Seventeen Network Infrastructure**

*A CSE421 Network Design Project*

</div>
