# network_design_and_implementation
(PUTTY | MICROSFT VISIO)

Design and implementation of a company's network project.  Equipment: Routers, Switches, PCs, Servers.  Implemented settings: GRE VPN, OSPF, hostnames, encrypted password, interfaces, clock rate, login, spanning tree, VLANs, ACL, GRE Tunnel, NAT, DNS, PPPoE, ISP2. 

1. Introdução

	Neste projecto vamos simular uma empresa comercial no ramo de vendas de automóveis que passou por um processo de expansão, onde houve a necessidade de informatização e interligação da sede e 3 filiais através da Internet.
	











































2. Descrição

O escritório, que antes contava com apenas a matriz composta por um posto de venda, com 1 gerente 1assistente de caixa e 1 técnico de júnior de informática e possuía apenas 3 computadores com 2 impressoras deskjet e um único acesso à Internet, via linha discada (256 Kbps), passou a ser composto por uma matriz e três filiais.

Com o processo de expansão, houve, também a necessidade de contratação de pessoal. Contratação de 1 Técnico Senior(Administrador de TI), para a empresa no geral e contratação e movimentação de 3 técnicos júnior(TI), 3 operadores de computador/webmaster e 3 gerentes para a filiais.

Sendo assim, a matriz passou a ser composta por 1 Técnico Sénior, 1 técnico júnior, 1 operador de computador/webmaster e 1 secretária.. As filiais foram composta por 1 técnico sénior(2), 1 operador de computador/webmaster, 1 secretária.

A Direcção da empresa solicitou um projeto de implementação de tuneis entre as filiais que atendesse às necessidades da empresa, de forma a ter a melhor relação custo-benefício possível. Foi informado ainda que deve ter a possibilidade de realização de comunicação via telefónica de baixo custo e video conferência.

O escritório matriz fica localizado na “cidade Y” e as filiais no centro Administrativo Técnico da “cidade X”. Com base nessas informações, foi apresentada a proposta para a implantação do “Projecto TELECOM 2018”, conforme adiante.

2.1 Situação da empresa

Situação da empresa “antes” da implantação do projecto:
Apenas a matriz: 1 Gerente, 1 Técnico Júnior e 1 Assistente.
Equipamentos: 3 computadores, 1 acesso à Internet via modem 64 Kbps e 2 impressora LaserJet 200dn.
Situação da empresa “após” a implantação do projecto:
Matriz: 2 Técnico Sénior (Administrador de TI), 2 Técnico Júnior de TI, e 2 Operador/WebMaster.
Filial: 1 Técnico Sénior(2), 2 Técnico Júnior, 2 Operador/WebMaster

2.2 Equipamentos Adqueridos e distribuição por equipamentos

- EQUIPAMENTOS ADQUERIDOS
6 Roteardores C1941
4 Switches C2960
20 Computadores
1 Servidor
- DISTRIBUIÇÃO POR EQUIPAMENTOS
MATRIZ:
1 Roteador C1941
1 Switche SW2960
Suporte para 10 PCs
FILIAL-A:
1 Roteador C1941
1 Switche C2960
Suporte para 20 PCs
FILIAL-B:
1 Roteador C1941
1 Switche C2960
Suporte para 60 PCs
FILIAL-C:
1 Roteador C1941
1 Switche C2960
Suporte para 80 PCs
ISP1:
1 Roteador C1491
ISP2:
1 Roteador C1491

3. Estrutura física e lógica da rede
3.1 Estrutura física

	Mais abaixo teremos o desenho da topologia física da rede que vai nos mostrar uma verdadeira aparência ou layout da rede. Ela vai nos representar como as redes estão conectadas, e o meio de conexão dos dispositivos. A forma de como os cabos estão conectados vai nos influênciar em diversos pontos considerados críticos, como a flexibilidade, velocidade, e segurança. Usamos a ferramenta Microsoft Visio 2016. 
 
3.1 Estrutura lógica

	A topologia lógica, refere-se à maneira de como os sinais agem sobre os meios de rede, ou a maneira como os dados são transmitidos através da rede a partir de um dispositivo para outro sem ter em conta a interligação física dos dispositivos. Elas são frequentemente associadas à Media Access Control, métodos e protocolos. Essas topologias são capazes de serem reconfiguradas dinamicamente por tipos especias de equipamentos como roteadores e switches. Usamos a ferramenta Microsoft Visio 2016. 



4. Planta baixa da rede

	A planta baixa é fundamental para que possamos ter a base correcta para a realização do projecto, no qual diz respeito a disposição física dos equipamentos. 
 

5. Tabela de endereçamento
tabela de Endereçamento
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

6. Objectivo da actividade

•	Configurar um túnel ponto a ponto de VPN GRE não criptografado e verificar se o tráfego da rede usa o túnel.
•	Configurar o protocolo de roteamento OSPF dentro do túnel VPN GRE.
•	Configure o hostname.
•	Perform basic configuration tasks on a router.
•	Atribua class como a senha criptografada do modo EXEC privilegiado
•	Configurar e activar interfaces.
•	Defina clock rate como 128000 para as interfaces seriais DCE
•	Atribua cisco como console e vty como senha e permita o login.
•	Configurar Spanning Tree Protocol.
•	Configurar VLANs nos switches.
•	Criar VLANs 10,20 e 30 para as redes das filiais B e C com a seguinte informação
Designação 	ID 	Network 	Prefix 	Root Bridge
Dados 	10 	YES 	YES 	S2
Servidores 	20 	YES 	YES 	S1
Gestão 	30 	YES 	YES 	S3
•	Configurar o roteamento OSPF nos roteadores Locais.
•	Atribua um endereço IP para cada loopback usando no primeiro octecto o ID do respectivo loopback.
•	Aplicar ACL Extendida para negar pacotes de Internet a Vlan 10
•	Configurar Túnnel GRE de Matriz (s0/0/0) à Filial A
•	Configurar Túnnel GRE de FILIAL-A (s0/0/0) à Filial-B
•	Configurar e verificar a sobrecarga do pool do NAT em MATRIZ
•	Configurar ACL em Matriz para permitir acesso internet a empresa
•	Configurar DNS e registar os hosts em MATRIZ
•	Configure PPPoE de ISP2 a FILIALC



7. Cenário

	Neste projecto , vamos configurar um túnel ponto a ponto de VPN GRE não criptografado e verificará se o tráfego da rede usa o túnel. Vamos também configurar o protocolo de roteamento OSPF dentro do túnel VPN GRE. O túnel GRE fica entre os roteadores MATRIZ e FILIAL-1 na área do OSPF 0. O ISP-1 não tem conhecimento do túnel GRE. A comunicação entre os roteadores MATRIZ e FILIAL-1 e o ISP1é realizada por meio de rotas estáticas padrão.


8. Tarefa 

Etapa 1: Cabeamos uma rede de maneira semelhante à presente no diagrama de topologia.  
Etapa 2: Apagamos todas as configurações existentes nos roteadores. 
Tarefa 2: Executamos configurações básicas dos dispositivos. Configuramos os roteadores MATRIZ, MATRIZ A, MATRIZ B, e MATRIZ C e os switches S1, S2, S3, S4, S5 e ainda do ISP1 e ISP2 de acordo com as seguintes diretrizes: 
• Configuramos o hostname nos equipamentos com os seguintes comandos:
>en
#conf t
#hostname [nome do host]
• Configuramos uma senha no modo EXEC como "class".
#enable secret class
#do wr
#exit
 • Configure o seguinte banner de mensagem do dia: “Acesso não autorizado é expressamente proibido e será punido nos termos da lei".
#conf t
#service password-encryption 
#banner motd # Acesso não autorizado é expressamente proibido e será punido nos #termos da lei#  
#end
• Configure uma senha para as conexões de console.
#line console 0
#password cisco senha
#login
#exit
• Configure o log síncrono.
#loggin Synchronous
#exit
• Configure uma senha para as conexões vty. 
#line vty 0 15 
#password cisco
#login
• Salve a configuração de execução na NVRAM.
#do wr
#exit

Etapa 3: Configurar interfaces
ETHERNET -> nos PCs
FASTETHERNET -> nos roteadores e switch
#interface fa X/X
#ip add x.x.x.x y.y.y.y
#no shut down
SERIAL -> nos roteadores e switch
#interface sx/x
#ip address x.x.x.x y.y.y.y
#no shutdown
GIGABYTE -> nos roteadores e switch
#interface gi x/x/x
#ip address x.x.x.x y.y.y.y
#no shutdown

• Defina clock rate como 128000 para as interfaces seriais DCE
#Interface serial x/x/X
#Clock rate 128000
•Configurar Spanning Tree Protocol.
#set spantree root 1
#set spantree root 10
#set spantree root 20
#set spantree root 30
•Configurar VLANs nos switches FILIAL B e FILIAL C
#vlan 50
#name gerenciamento
#int vlan 50
#ip add x.x.x.x y.y.y.y
#no shut
#exit
#ip default-gateway x.x.x.x
#ip name-server x.x.x.x

! criando as VLANs dos departamentos

#vlan 10
#name Dados
#vlan 20
#name Servidores
#vlan 30
#name Gestao

! Fazendo a alocacao de portas - membership

#int range fast 0/1 - 15
#switchport mode access
#switchport access vlan 10
#int range fast 0/16 - 20
#switchport mode access
#switchport access vlan 20
#int range fast 0/21 - 24
#witchport mode access
#switchport access vlan 30
•    Configurar o roteamento OSPF nos roteadores Locais
>en
#conf t
#router ospf 1
#network x.x.x.x m.m.m.m area 0
#network x.x.x.x m.m.m.m area 0
#end
#wr
•    Aplicar ACL Extendida para negar  pacotes de Internet a Vlan 10
#conf t
#access-list 1 deny ip [mascara] [curinga]
#end
#wr  
•    Configurar Túnnel GRE  de Matriz (s0/0/0) à Filial A
Matriz 
#conf t
#interface tunnel 1
#ip add x.x.x.x y.y.y.y
#tunnel destination x.x.x.x
#tunnel source x.x.x.x
#ip route x.x.x.x y.y.y.y x.x.x.x
Filial A
#conf t
#interface tunnel 1
#ip add x.x.x.x y.y.y.y
#tunnel destination x.x.x.x
#tunnel source x.x.x.x
#ip route x.x.x.x y.y.y.y x.x.x.x
Matriz 
#Conf t
#Router eigrp 20
#Network x.x.x.x
#network x.x.x.x
#no auto-summary
Filial A
#Conf t
#Router eigrp 20
#Network x.x.x.x
#network x.x.x.x
#no auto-summary
•    Configurar Túnnel GRE  de FILIAL-A (s0/0/0) à Filial-B
Filial A
#conf t
#interface tunnel 1
#ip add x.x.x.x y.y.y.y
#tunnel destination x.x.x.x
#tunnel source x.x.x.x
#ip route x.x.x.x y.y.y.y x.x.x.x
Filial B
#conf t
#interface tunnel 1
#ip add x.x.x.x y.y.y.y
#tunnel destination x.x.x.x
#tunnel source x.x.x.x
#ip route x.x.x.x y.y.y.y x.x.x.x
Filial A
#Conf t
#Router eigrp 20
#Network x.x.x.x
#network x.x.x.x
#no auto-summary
Filial B
#Conf t
#Router eigrp 20
#Network x.x.x.x
#network x.x.x.x
#no auto-summary
 
•    Configurar e verificar a sobrecarga do pool do NAT em MATRIZ 
#en
#conf t
#ip nat pool CCNA4 x.x.x.x x.x.x.x netmask y.y.y.y
#ip nat inside source list 1 pool CCNA4 overload
#interface fa0/0
#ip nat inside
#no shut
#exit
#interface se0/1/0
ip nat outside
#no shut
•    Configurar ACL em Matriz para permitir acesso internet a empresa 
#access-list 1 permit x.x.x.x
#int se0/1/0
#ip access-group 1 out
#end
#wr
•    Configurar DNS e registar os hosts em MATRIZ 
•    Configure PPPoE de ISP2 a FILIALC


