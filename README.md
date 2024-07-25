# Network Design and Implementation
(CISCO ROUTERS AND SWITCHES | PUTTY | MICROSFT VISIO)

Design and implementation of a company's network project. Equipment: Routers, Switches, PCs, Servers. Implemented settings: GRE VPN, OSPF, hostnames, encrypted password, interfaces, clock rate, login, spanning tree, VLANs, ACL, GRE Tunnel, NAT, DNS, PPPoE, ISP2.

**1. Introduction**

In this project, a commercial company in the car sales sector needed to expand. The headquarters and three branches needed to be computerized and interconnected via the Internet.

**2. Description**

The office, which previously had only the head office consisting of a sales station, with one manager, one cashier assistant and one junior IT technician, had only three computers with two Deskjet printers and single Internet access via dial-up line ( 256 Kbps), now consists of a head office and three branches.

With the expansion process, there was also a need to hire staff. We hired and moved one Senior Technician (IT Administrator) for the company in general, three junior technicians (IT), three computer operators/webmasters, and three managers for branches.

Therefore, the head office was now composed of one Senior Technician, one junior technician, one computer operator/webmaster, and one secretary. The branches were composed of one senior technician(2), one computer operator/webmaster, and one secretary.

The company's Management requested a project to implement tunnels between branches that would meet the company's needs and have the best possible cost-benefit ratio. It was also informed that it must be possible to communicate via low-cost telephone and video conference.

The main office is located in “City Y,” and the branches are in the Technical Administrative Center of “City X.” Based on this information, the proposal for implementing the “TELECOM Project 2018” was presented as follows.

**2.1 Company situation**
<br>Situation of the company “before” the implementation of the project:
<br>Just the head office: 1 Manager, 1 Junior Technician and 1 Assistant.
<br>Equipment: 3 computers, 1 Internet access via 64 Kbps modem and 2 LaserJet 200dn printers.
<br>Situation of the company “after” the implementation of the project:
<br>Headquarters: 2 Senior Technician (IT Administrator), 2 Junior IT Technician, and 2 Operator/WebMaster.
<br>Branch: 1 Senior Technician(2), 2 Junior Technician, 2 Operator/WebMaster

**2.2 Purchased Equipment and distribution by equipment**

**- EQUIPMENT ACQUIRED**
<br>6 C1941 Routers
<br>4 C2960 Switches
<br>20 Computers
<br>1 Server

**- DISTRIBUTION BY EQUIPMENT**

**HEADQUARTERS:**
<br>1 C1941 Router
<br>1 Switch SW2960
<br>Support for 10 PCs

**BRANCH-A:**
<br>1 C1941 Router
<br>1 Switch C2960
<br>Support for 20 PCs

**BRANCH-B:**
<br>1 C1941 Router
<br>1 Switch C2960
<br>Support for 60 PCs

**BRANCH-C:**
<br>1 C1941 Router
<br>1 Switch C2960
<br>Support for 80 PCs

**ISP1:**
<br>1 C1491 Router

**ISP2:**
<br>1 C1491 Router

**3. Physical and logical structure of the network**

**3.1 Physical structure**

Below is a drawing of the network's physical topology that will show us its true appearance or layout. It will represent how the networks are connected and the means of connecting the devices. The cables' connection will influence several critical points, such as flexibility, speed, and security. I use the Microsoft Visio 2016 tool.

 ![image](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/ac8d99f4-5ecc-416a-b793-963e37ccd18c)

**3.2 Logical structure**

Logical topology refers to the way signals act on network media or the way data is transmitted over the network from one device to another without taking into account the physical interconnection of the devices. It is often associated with Media Access Control methods and protocols. These topologies can be dynamically reconfigured by special types of equipment, such as routers and switches. I use the Microsoft Visio 2016 tool.

![02](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/c77bd5f2-0a68-437a-b4c1-5792a940de06)


**4. Network floor plan**

The floor plan is essential so that I can have the correct basis for carrying out the project, which concerns the physical arrangement of the equipment.

![03](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/f399f2e0-4119-4431-93e8-c6ca566332ed)


**5. Addressing table**
![04](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/c1ea62ba-7c10-4926-80c3-adbff74edda9)


LAN A, B and C addressing table with IP 172.31.0.0/18
![05](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/33c1b4c0-9f9a-4144-8197-e24d36960455)


**6. Objective of the activity**
<br>• Configure an unencrypted GRE VPN point-to-point tunnel and verify that network traffic uses the tunnel.
<br>• Configure the OSPF routing protocol within the GRE VPN tunnel.
<br>• Configure the hostname.
<br>• Perform basic configuration tasks on a router.
<br>• Assign class as the privileged EXEC mode encrypted password
<br>• Configure and activate interfaces.
<br>• Set clock rate to 128000 for DCE serial interfaces
<br>• Assign cisco as console and vty as password and allow login.
<br>• Configure Spanning Tree Protocol.
<br>• Configure VLANs on switches.
<br>• Create VLANs 10,20 and 30 for the B and C branch networks with the following information:
![06](https://github.com/jose-ambrosioo/network_design_and_implementation/assets/59221796/3ca179b7-b4ad-4fb3-91ba-3ad0c68d764e)

<br>• Configure OSPF routing on Local routers.
<br>• Assign an IP address to each loopback using the ID of the respective loopback in the first octet.
<br>• Apply Extended ACL to deny Internet packets to Vlan 10
<br>• Configure GRE Tunnel from Headquarters (s0/0/0) to Branch A
<br>• Configure GRE Tunnel from BRANCH-A (s0/0/0) to Branch-B
<br>• Configure and check NAT pool overload in Headquarters/MATRIZ
<br>• Configure ACL on Matrix to allow internet access to the company
<br>• Configure DNS and register hosts in Headquarters/MATRIZ
<br>• Configure PPPoE from ISP2 to BRANCH


**7. Scenario**

In this project, I configured an unencrypted GRE VPN point-to-point tunnel and verified that network traffic uses it. I will also configure the OSPF routing protocol inside the GRE VPN tunnel. The GRE tunnel is between the HOME and BRANCH-1 routers in OSPF area 0. ISP-1 is not aware of the GRE tunnel. Communication between the HEADPHONE and BRANCH-1 routers and ISP1 is carried out using standard static routes.


**8. Task**

**Step 1: I wired the network in a similar way to the one in the topology diagram.**

**Step 2: I erased all existing settings on the routers.**

**Step 3: I performed basic device configurations. I configure the HEAD OFFICE, BRANCH A, BRANCH B, and BRANCH C routers and the S1, S2, S3, S4, S5 and ISP1 and ISP2 switches according to the following guidelines:**

• Configure the hostname on the equipment with the following commands:
<br>>en
<br>#conf t
<br>#hostname [nome do host]
<br>• Set a password in EXEC mode to "class".
<br>#enable secret class
<br>#do wr
<br>#exit

• Configure the following Message of the Day banner: “Unauthorized access is expressly prohibited and will be punished in accordance with the law.”
<br>#conf t
<br>#service password-encryption 
<br>#banner motd <br># Unauthorized access is expressly prohibited and will be punished under the law<br>#  
<br>#end

• Configure a password for console connections.
<br>#line console 0
<br>#password cisco senha
<br>#login
<br>#exit

• Configure synchronous logging.
<br>#loggin Synchronous
<br>#exit
<br>• Set a password for vty connections.
<br>#line vty 0 15 
<br>#password cisco
<br>#login
<br>• Save the run configuration to NVRAM.
<br>#do wr
<br>#exit

**Step 4: Configure interfaces**

ETHERNET -> on PCs
<br>FASTETHERNET -> on routers and switches
<br>#interface fa X/X
<br>#ip add x.x.x.x y.y.y.y
<br>#no shut down
<br>SERIAL -> on routers and switches
<br>#interface sx/x
<br>#ip address x.x.x.x y.y.y.y
<br>#no shutdown
<br>GIGABYTE -> on routers and switches
<br>#interface gi x/x/x
<br>#ip address x.x.x.x y.y.y.y
<br>#no shutdown

• Set clock rate to 128000 for DCE serial interfaces
<br>#Interface serial x/x/X
<br>#Clock rate 128000

• Configure Spanning Tree Protocol.
<br>#set spantree root 1
<br>#set spantree root 10
<br>#set spantree root 20
<br>#set spantree root 30

• Configure VLANs on BRANCH B and BRANCH C switches
<br>#vlan 50
<br>#name gerenciamento
<br>#int vlan 50
<br>#ip add x.x.x.x y.y.y.y
<br>#no shut
<br>#exit
<br>#ip default-gateway x.x.x.x
<br>#ip name-server x.x.x.x

! creating departmental VLANs
<br>#vlan 10
<br>#name Dados
<br>#vlan 20
<br>#name Servidores
<br>#vlan 30
<br>#name Gestao

! Allocating ports - membership
<br>#int range fast 0/1 - 15
<br>#switchport mode access
<br>#switchport access vlan 10
<br>#int range fast 0/16 - 20
<br>#switchport mode access
<br>#switchport access vlan 20
<br>#int range fast 0/21 - 24
<br>#witchport mode access
<br>#switchport access vlan 30

•    Configure OSPF Routing on Local Routers
>en
<br>#conf t
<br>#router ospf 1
<br>#network x.x.x.x m.m.m.m area 0
<br>#network x.x.x.x m.m.m.m area 0
<br>#end
<br>#wr

•    Apply Extended ACL to deny Internet packets to Vlan 10
<br>#conf t
<br>#access-list 1 deny ip [mascara] [curinga]
<br>#end
<br>#wr

•    Configure GRE Tunnel from Headquarters (s0/0/0) to Branch A
<br>Head Office 
<br>#conf t
<br>#interface tunnel 1
<br>#ip add x.x.x.x y.y.y.y
<br>#tunnel destination x.x.x.x
<br>#tunnel source x.x.x.x
<br>#ip route x.x.x.x y.y.y.y x.x.x.x
<br>Branch A
<br>#conf t
<br>#interface tunnel 1
<br>#ip add x.x.x.x y.y.y.y
<br>#tunnel destination x.x.x.x
<br>#tunnel source x.x.x.x
<br>#ip route x.x.x.x y.y.y.y x.x.x.x
<br>Head Office 
<br>#Conf t
<br>#Router eigrp 20
<br>#Network x.x.x.x
<br>#network x.x.x.x
<br>#no auto-summary
<br>Branch A
<br>#Conf t
<br>#Router eigrp 20
<br>#Network x.x.x.x
<br>#network x.x.x.x
<br>#no auto-summary

•    Configure GRE Tunnel from BRANCH-A (s0/0/0) to Branch-B
<br>Branch A
<br>#conf t
<br>#interface tunnel 1
<br>#ip add x.x.x.x y.y.y.y
<br>#tunnel destination x.x.x.x
<br>#tunnel source x.x.x.x
<br>#ip route x.x.x.x y.y.y.y x.x.x.x
<br>Branch B
<br>#conf t
<br>#interface tunnel 1
<br>#ip add x.x.x.x y.y.y.y
<br>#tunnel destination x.x.x.x
<br>#tunnel source x.x.x.x
<br>#ip route x.x.x.x y.y.y.y x.x.x.x
<br>Branch A
<br>#Conf t
<br>#Router eigrp 20
<br>#Network x.x.x.x
<br>#network x.x.x.x
<br>#no auto-summary
<br>Branch B
<br>#Conf t
<br>#Router eigrp 20
<br>#Network x.x.x.x
<br>#network x.x.x.x
<br>#no auto-summary
 
•    Configure and Check NAT Pool Overload in HEAD OFFICE
<br>#en
<br>#conf t
<br>#ip nat pool CCNA4 x.x.x.x x.x.x.x netmask y.y.y.y
<br>#ip nat inside source list 1 pool CCNA4 overload
<br>#interface fa0/0
<br>#ip nat inside
<br>#no shut
<br>#exit
<br>#interface se0/1/0
<br>ip nat outside
<br>#no shut

•    Configure ACL on Matrix to allow internet access to the company 
<br>#access-list 1 permit x.x.x.x
<br>#int se0/1/0
<br>#ip access-group 1 out
<br>#end
<br>#wr

•    Configure DNS and register hosts in Headquarters/MATRIZ

•    Configure PPPoE from ISP2 to BRANCH C
