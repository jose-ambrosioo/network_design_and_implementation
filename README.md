# network_design_and_implementation
(PUTTY | MICROSFT VISIO)

Design and implementation of a company's network project. Equipment: Routers, Switches, PCs, Servers. Implemented settings: GRE VPN, OSPF, hostnames, encrypted password, interfaces, clock rate, login, spanning tree, VLANs, ACL, GRE Tunnel, NAT, DNS, PPPoE, ISP2.

1. Introduction

In this project we will simulate a commercial company in the car sales sector that went through an expansion process, where there was a need for computerization and interconnection of the headquarters and 3 branches via the Internet.


2. Description

The office, which previously had only the head office consisting of a sales station, with 1 manager, 1 cashier assistant and 1 junior IT technician and had only 3 computers with 2 deskjet printers and a single Internet access, via dial-up line ( 256 Kbps), now consists of a head office and three branches.

With the expansion process, there was also a need to hire staff. Hiring 1 Senior Technician (IT Administrator) for the company in general and hiring and moving 3 junior technicians (IT), 3 computer operators/webmaster and 3 managers for branches.

Therefore, the head office was now composed of 1 Senior Technician, 1 junior technician, 1 computer operator/webmaster and 1 secretary. The branches were composed of 1 senior technician(2), 1 computer operator/webmaster, 1 secretary .

The company's Management requested a project to implement tunnels between branches that would meet the company's needs, in order to have the best possible cost-benefit ratio. It was also informed that it must be possible to communicate via low-cost telephone and video conference.

The main office is located in “city Y” and the branches in the Technical Administrative center of “city X”. Based on this information, the proposal for the implementation of the “TELECOM Project 2018” was presented, as follows.

2.1 Company situation

Situation of the company “before” the implementation of the project:
Just the head office: 1 Manager, 1 Junior Technician and 1 Assistant.
Equipment: 3 computers, 1 Internet access via 64 Kbps modem and 2 LaserJet 200dn printers.
Situation of the company “after” the implementation of the project:
Headquarters: 2 Senior Technician (IT Administrator), 2 Junior IT Technician, and 2 Operator/WebMaster.
Branch: 1 Senior Technician(2), 2 Junior Technician, 2 Operator/WebMaster

2.2 Purchased Equipment and distribution by equipment

- EQUIPMENT ACQUIRED
6 C1941 Routers
4 C2960 Switches
20 Computers
1 Server
- DISTRIBUTION BY EQUIPMENT
HEADQUARTERS:
1 C1941 Router
1 Switch SW2960
Support for 10 PCs
BRANCH-A:
1 C1941 Router
1 Switch C2960
Support for 20 PCs
BRANCH-B:
1 C1941 Router
1 Switch C2960
Support for 60 PCs
BRANCH-C:
1 C1941 Router
1 Switch C2960
Support for 80 PCs
ISP1:
1 C1491 Router
ISP2:
1 C1491 Router

3. Physical and logical structure of the network
3.1 Physical structure

Below we will have the drawing of the physical topology of the network that will show us a true appearance or layout of the network. It will represent to us how the networks are connected, and the means of connecting the devices. The way the cables are connected will influence several points considered critical, such as flexibility, speed, and security. We use the Microsoft Visio 2016 tool.
 
3.1 Logical structure

Logical topology refers to the way in which signals act on network media, or the way in which data is transmitted over the network from one device to another without taking into account the physical interconnection of the devices. They are often associated with Media Access Control, methods and protocols. These topologies are capable of being dynamically reconfigured by special types of equipment such as routers and switches. We use the Microsoft Visio 2016 tool.



4. Network floor plan

The floor plan is essential so that we can have the correct basis for carrying out the project, which concerns the physical arrangement of the equipment.
 

5. Addressing table
Addressing table
Dispositivo 	Interface 	Endereço IP 	Gateway padrão
MATRIZ 	G0/1 	172.16.1.1/24 	N/A
S0/0/0 (DCE) 	10.1.1.1/30 	N/A	
Tunnel0 	172.16.12.1/30 	N/A	
ISP1 	S0/0/0 	10.1.1.2/30 	N/A
S0/0/1 (DCE) 	10.2.2.2/30 	N/A	
FILIAL-A 	G0/1 	172.16.2.1/24 	N/A
S0/0/1 	10.2.2.1/30 	N/A	
Tunnel0 	172.16.12.2/30 	N/A	
PC-A 	NIC 	172.16.1.3/24 	YES
PC-C 	NIC 	172.16.2.3/24 	YES
FILIAL-B	S0/0/0(DCE) 	11.11.1.1/30 	N/A
G0/1 	DOT1Q 	YES	
FILIA - C	S0/0/0 	11.11.1.2/30 	N/A
G0/1 	YES 	N/A	
IPS2 	G0/1 	YES 	N/A

Tabela de endereçamento da LAN A, B e C com o IP 172.31.0.0/18
Dispositivo 	Interface 	Endereço IP 	Mácara de sub-rede	Gateway padrão
200 host		172.24.0.0/24	255.255.255.0	
80 host		172.24.1.0/25	255.255.255.8	
60 host		172.24.1.128/25	255.225.255.8	

6. Objective of the activity

• Configure an unencrypted GRE VPN point-to-point tunnel and verify that network traffic uses the tunnel.
• Configure the OSPF routing protocol within the GRE VPN tunnel.
• Configure the hostname.
• Perform basic configuration tasks on a router.
• Assign class as the privileged EXEC mode encrypted password
• Configure and activate interfaces.
• Set clock rate to 128000 for DCE serial interfaces
• Assign cisco as console and vty as password and allow login.
• Configure Spanning Tree Protocol.
• Configure VLANs on switches.
• Create VLANs 10,20 and 30 for the B and C branch networks with the following information
Designation ID Network Prefix Root Bridge
Dice 10 YES YES S2
Servers 20 YES YES S1
Management 30 YES YES S3
• Configure OSPF routing on Local routers.
• Assign an IP address to each loopback using the ID of the respective loopback in the first octet.
• Apply Extended ACL to deny Internet packets to Vlan 10
• Configure GRE Tunnel from Headquarters (s0/0/0) to Branch A
• Configure GRE Tunnel from BRANCH-A (s0/0/0) to Branch-B
• Configure and check NAT pool overload in MATRIZ
• Configure ACL on Matrix to allow internet access to the company
• Configure DNS and register hosts in MATRIZ
• Configure PPPoE from ISP2 to BRANCH



7. Scenario

In this project, we will configure an unencrypted GRE VPN point-to-point tunnel and verify that network traffic uses it. We will also configure the OSPF routing protocol inside the GRE VPN tunnel. The GRE tunnel is between the HOME and BRANCH-1 routers in OSPF area 0. ISP-1 is not aware of the GRE tunnel. Communication between the HEADPHONE and BRANCH-1 routers and ISP1 is carried out using standard static routes.


8. Task

Step 1: We wired a network in a similar way to the one in the topology diagram.
Step 2: We erased all existing settings on the routers.
Task 2: We performed basic device configurations. We configure the MATRIZ, MATRIZ A, MATRIZ B, and MATRIZ C routers and the S1, S2, S3, S4, S5 and ISP1 and ISP2 switches according to the following guidelines:
