Router 1

enable
configure terminal
hostname R1
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface gigabitEthernet 0/1
ip address 192.168.0.1 255.255.224.0
description REDE 192.168.0.0/19
no shutdown
exit
interface gigabitEthernet 0/1.10
encapsulation dot1q 10
ip address 192.168.0.1 255.255.248.0
description REDE 192.168.0.0/21
no shutdown
exit
interface gigabitEthernet 0/1.20
encapsulation dot1q 20
ip address 192.168.8.1 255.255.252.0
description REDE 192.168.8.0/22
no shutdown
exit
interface gigabitEthernet 0/1.30
encapsulation dot1q 30
ip address 192.168.12.1 255.255.254.0
description REDE 192.168.12.0/23
no shutdown
exit
interface gigabitEthernet 0/1.40
encapsulation dot1q 40
ip address 192.168.14.1 255.255.255.128
description REDE 192.168.14.0/25
no shutdown
exit
interface serial 0/0/1
ip address 201.187.89.5 255.255.255.252
description REDE 201.187.89.4/30
no shutdown
interface serial 0/1/1
ip address 201.187.89.21 255.255.255.252
description REDE 201.187.89.20/30
no shutdown
interface serial 0/0/0
ip address 201.187.89.1 255.255.255.252
description REDE 201.187.89.0/30
no shutdown
exit
ip route 10.0.0.0 255.0.0.0 201.187.89.2
ip route 10.0.0.0 255.0.0.0 201.187.89.6
ip route 10.0.0.0 255.0.0.0 201.187.89.22
ip route 172.16.0.0 255.240.0.0 201.187.89.2
ip route 172.16.0.0 255.240.0.0 201.187.89.6
ip route 172.16.0.0 255.240.0.0 201.187.89.22
ip route 192.168.32.0 255.255.248.0 201.187.89.2
ip route 192.168.32.0 255.255.248.0 201.187.89.6
ip route 192.168.32.0 255.255.248.0 201.187.89.22
ip route 201.187.89.8 255.255.255.252 201.187.89.2
ip route 201.187.89.8 255.255.255.252 201.187.89.6
ip route 201.187.89.8 255.255.255.252 201.187.89.22
ip route 201.187.89.16 255.255.255.252 201.187.89.2
ip route 201.187.89.16 255.255.255.252 201.187.89.6
ip route 201.187.89.16 255.255.255.252 201.187.89.22
ip route 201.187.89.12 255.255.255.252 201.187.89.2
ip route 201.187.89.12 255.255.255.252 201.187.89.6
ip route 201.187.89.12 255.255.255.252 201.187.89.22
do wr


Router 2

enable
configure terminal
hostname R2
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface gigabitEthernet 0/1
ip address 10.0.0.1 255.0.0.0
description REDE 10.0.0.0/8
no shutdow
exit
interface gigabitEthernet 0/1.50
encapsulation dot1Q 50
ip address 10.0.0.1 255.255.128.0
description REDE 10.0.0.0/17
no shutdown
exit
interface gigabitEthernet 0/1.60
encapsulation dot1Q 60
ip address 10.0.128.1 255.255.224.0
description REDE 10.0.128.0/19
no shutdown
exit
interface gigabitEthernet 0/1.70
encapsulation dot1Q 70
ip address 10.0.160.1 255.255.248.0
description REDE 10.0.160.0/21
no shutdown
exit
interface gigabitEthernet 0/1.80
encapsulation dot1Q 80
ip address 10.0.168.1 255.255.254.0
description REDE 10.0.168.0/23
no shutdown
exit
interface serial 0/0/1
ip address 201.187.89.6 255.255.255.252
description REDE 201.187.89.4/30
no shutdown
interface serial 0/1/1
ip address 201.187.89.17 255.255.255.252
description REDE 201.187.89.16/30
no shutdown
interface serial 0/0/0
ip address 201.187.89.9 255.255.255.252
description REDE 201.187.89.8/30
no shutdown
exit
ip route 192.168.0.0 255.255.224.0 201.187.89.2
ip route 192.168.0.0 255.255.224.0 201.187.89.5
ip route 192.168.0.0 255.255.224.0 201.187.89.10
ip route 172.16.0.0 255.240.0.0 201.187.89.2
ip route 172.16.0.0 255.240.0.0 201.187.89.5
ip route 172.16.0.0 255.240.0.0 201.187.89.10
ip route 192.168.32.0 255.255.248.0 201.187.89.2
ip route 192.168.32.0 255.255.248.0 201.187.89.5
ip route 192.168.32.0 255.255.248.0 201.187.89.10
ip route 201.187.89.20 255.255.255.252 201.187.89.2
ip route 201.187.89.20 255.255.255.252 201.187.89.5
ip route 201.187.89.20 255.255.255.252 201.187.89.10
ip route 201.187.89.0 255.255.255.252 201.187.89.2
ip route 201.187.89.0 255.255.255.252 201.187.89.5
ip route 201.187.89.0 255.255.255.252 201.187.89.10
ip route 201.187.89.12 255.255.255.252 201.187.89.2
ip route 201.187.89.12 255.255.255.252 201.187.89.5
ip route 201.187.89.12 255.255.255.252 201.187.89.10
do wr


Router 3

enable
configure terminal
hostname R3
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username Thiago privilege 15 secret thiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface gigabitEthernet 0/1
ip address 192.168.32.1 255.255.248.0
description REDE 192.168.32.0/21
no shutdown
exit
interface gigabitEthernet 0/1.80
encapsulation dot1Q 80
ip address 192.168.32.1 255.255.252.0
description REDE 192.168.32.0/22
no shutdown
exit
interface gigabitEthernet 0/1.60
encapsulation dot1Q 60
ip address 192.168.36.1 255.255.254.0
description REDE 192.168.36.0/23
no shutdown
exit
interface gigabitEthernet 0/1.88
encapsulation dot1Q 88
ip address 192.168.38.1 255.255.255.0
description REDE 192.168.38.0/24
no shutdown
exit
interface gigabitEthernet 0/1.100
encapsulation dot1Q 100
ip address 192.168.39.1 255.255.255.192
description REDE 10.0.168.0/23
no shutdown
exit
interface serial 0/0/1
ip address 201.187.89.12 255.255.255.252
description REDE 201.187.89.12/30
no shutdown
interface serial 0/1/1
ip address 201.187.89.20 255.255.255.252
description REDE 201.187.89.20/30
no shutdown
interface serial 0/0/0
ip address 201.187.89.8 255.255.255.252
description REDE 201.187.89.8/30
no shutdown
exit
ip route 192.168.0.0 255.255.224.0 201.187.89.21
ip route 192.168.0.0 255.255.224.0 201.187.89.9
ip route 192.168.0.0 255.255.224.0 201.187.89.14
ip route 10.0.0.0 255.0.0.0 201.187.89.21
ip route 10.0.0.0 255.0.0.0 201.187.89.9
ip route 10.0.0.0 255.0.0.0 201.187.89.14
ip route 172.16.0.0 255.240.0.0 201.187.89.21
ip route 172.16.0.0 255.240.0.0 201.187.89.9
ip route 172.16.0.0 255.240.0.0 201.187.89.14
ip route 201.187.89.0 255.255.255.252 201.187.89.21
ip route 201.187.89.0 255.255.255.252 201.187.89.9
ip route 201.187.89.0 255.255.255.252 201.187.89.14
ip route 201.187.89.16 255.255.255.252 201.187.89.21
ip route 201.187.89.16 255.255.255.252 201.187.89.9
ip route 201.187.89.16 255.255.255.252 201.187.89.14
ip route 201.187.89.4 255.255.255.252 201.187.89.21
ip route 201.187.89.4 255.255.255.252 201.187.89.9
ip route 201.187.89.4 255.255.255.252 201.187.89.14
do wr


Router 4

enable
configure terminal
hostname R4
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
line vty 0 15
password SenhadaVTY
login
transport input ssh
exec-timeout 10
exit
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
interface gigabitEthernet 0/1
ip address 172.16.0.1 255.240.0.0
description REDE 172.16.0.0/12
no shutdown
exit
interface gigabitEthernet 0/1.88
encapsulation dot1Q 88
ip address 172.16.0.1 255.240.0.0
description REDE 172.16.0.0/12
no shutdown
exit
interface gigabitEthernet 0/1.88
encapsulation dot1Q 88
ip address 172.32.0.1 255.254.0.0
description REDE 172.32.0.0/15
no shutdown
exit
interface gigabitEthernet 0/1.200
encapsulation dot1Q 200
ip address 172.34.0.1 255.255.192.0
description REDE 172.34.0.0/18
no shutdown
exit
interface gigabitEthernet 0/1.90
encapsulation dot1Q 90
ip address 172.34.64.1
description REDE 172.34.64.0/23
no shutdown
exit
interface serial 0/0/1
ip address 201.187.89.14 255.255.255.252
description REDE 201.187.89.12/30
no shutdown
interface serial 0/1/1
ip address 201.187.89.18 255.255.255.252
description REDE 201.187.89.16/30
no shutdown
interface serial 0/0/0
ip address 201.187.89.2 255.255.255.252
description REDE 201.187.89.0/30
no shutdown
exit
ip route 192.168.0.0 255.255.224.0 201.187.89.1
ip route 192.168.0.0 255.255.224.0 201.187.89.13
ip route 192.168.0.0 255.255.224.0 201.187.89.17
ip route 192.168.32.0 255.255.248.0 201.187.89.1
ip route 192.168.32.0 255.255.248.0 201.187.89.13
ip route 192.168.32.0 255.255.248.0 201.187.89.17
ip route 10.0.0.0 255.0.0.0 201.187.89.1
ip route 10.0.0.0 255.0.0.0 201.187.89.13
ip route 10.0.0.0 255.0.0.0 201.187.89.17
ip route 201.187.89.4 255.255.255.252 201.187.89.1
ip route 201.187.89.4 255.255.255.252 201.187.89.13
ip route 201.187.89.4 255.255.255.252 201.187.89.17
ip route 201.187.89.8 255.255.255.252 201.187.89.1
ip route 201.187.89.8 255.255.255.252 201.187.89.13
ip route 201.187.89.8 255.255.255.252 201.187.89.17
ip route 201.187.89.20 255.255.255.252 201.187.89.1
ip route 201.187.89.20 255.255.255.252 201.187.89.13
ip route 201.187.89.20 255.255.255.252 201.187.89.17
do wr


SWITCH SWITCH SWITCH SWITCH

Switch 1

enable
configure terminal
hostname S1
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
vlan 10
name TESTES
exit
vlan 20
name TELEMARKETING
exit
vlan 30
name CONSULTORES
exit 
vlan 40 
name RH
exit
interface F0/1
switchport mode access
switchport access vlan 10
exit
interface vlan 10
ip address 192.168.0.3 255.255.248.0
description REDE 1
no shutdown
exit
interface F0/10
switchport mode access
switchport access vlan 20
exit
interface vlan 20
ip address 192.168.8.3 255.255.252.0
description REDE 1
no shutdown 
exit
interface F0/18
switchport mode access
switchport access vlan 30
exit
interface vlan 30
ip address 192.168.12.3 255.255.254.0
description REDE 1
no shutdown 
exit
interface F0/23
switchport mode access
switchport access vlan 40
exit
interface vlan 40
ip address 192.168.14.3 255.255.255.128
description REDE 1
no shutdown 
exit
interface G0/1
switchport mode trunk
switchport trunk native vlan 88
switchport trunk allowed vlan 10,20,30,40
no shutdown
exit
ip default-gateway 192.168.0.1
do wr


Switch 2

enable
configure terminal
hostname S2
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
vlan 50
name ANALISTAS
exit
vlan 60
name OPERACAO
exit
vlan 70
name TI
exit 
vlan 80
name ADMINISTRATIVO
exit
interface F0/1
switchport mode access
switchport access vlan 50
exit
interface vlan 50
ip address 10.0.0.3 255.255.128.0
description REDE 2
no shutdown
exit
interface F0/24
switchport mode access
switchport access vlan 60
exit
interface vlan 60
ip address 10.0.128.3 255.255.224.0
description REDE 2
no shutdown 
exit
interface F0/21
switchport mode access
switchport access vlan 70
exit
interface vlan 70
ip address 10.0.160.3 255.255.248.0
description REDE 2
no shutdown 
exit
interface F0/22
switchport mode access
switchport access vlan 80
exit
interface vlan 80
ip address 10.0.168.3 255.255.254.0
description REDE 2
no shutdown 
exit
interface G0/1
switchport mode trunk
switchport trunk native vlan 88
switchport trunk allowed vlan 50,60,70,80
no shutdown
exit
ip default-gateway 10.0.0.1
do wr


Switch 3

enable
configure terminal
hostname S3
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
vlan 80
name FINACAS
exit
vlan 60
name OPERACOES
exit
vlan 88
name RELOGIOS
exit 
vlan 100
name LIVRE
exit
interface F0/1
switchport mode access
switchport access vlan 80
exit
interface vlan 80
ip address 192.168.32.3 255.255.252.0
description REDE 3
no shutdown
exit
interface F0/6
switchport mode access
switchport access vlan 60
exit
interface vlan 60
ip address 192.168.36.3 255.255.254.0
description REDE 3
no shutdown 
exit
interface F0/10
switchport mode access
switchport access vlan 88
exit
interface vlan 88
ip address 192.168.38.3 255.255.255.0
description REDE 3
no shutdown 
exit
interface F0/20
switchport mode access
switchport access vlan 100
exit
interface vlan 100
ip address 192.168.39.3 255.255.255.192
description REDE 3
no shutdown 
exit
interface G0/1
switchport mode trunk
switchport trunk native vlan 88
switchport trunk allowed vlan 80,60,88,100
no shutdown
exit
ip default-gateway 192.168.32.1
do wr


Switch 4

enable
configure terminal
hostname S4
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username Thiago privilege 15 secret ThiagoSilva
username Estagiario privilege 1 secret Thiagoestagiario
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
exec-timeout 10
login local
exit
vlan 88
name SERVIDORES
exit
vlan 200
name VOZ
exit
vlan 90
name TACACS
exit 
vlan 88
name MONITORAMENTO
exit
interface F0/1
switchport mode access
switchport access vlan 88
exit
interface vlan 88
ip address 172.24.0.3 255.252.0.0
description REDE 4
no shutdown
exit
interface F0/10
switchport mode access
switchport access vlan 200
exit
interface vlan 200
ip address 172.28.0.3 255.255.128.0
description REDE 4
no shutdown 
exit
interface F0/13
switchport mode access
switchport access vlan 90
exit
interface vlan 90
ip address 172.28.128.3 255.255.254.0
description REDE 4
no shutdown 
exit
interface F0/15
switchport mode access
switchport access vlan 88
exit
interface vlan 88
ip address 172.16.0.3 255.248.0.0
description REDE 4
no shutdown 
exit
interface G0/1
switchport mode trunk
switchport trunk native vlan 88
switchport trunk allowed vlan 88,200,90,88
no shutdown
exit
ip default-gateway 172.16.0.1
do wr
