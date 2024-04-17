# CCNAv7 SRWE Skills Assessment

## switch ONE


### copy and paste for switch 1

configure terminal 
no ip domain-lookup 
hostname S1
ip domain-name ccna-lab.com
enable secret ciscoenpass 
line console 0
password ciscoconpass
login
exit
line vty 0 15
password ciscoconpass
login local
transport input ssh
exit 
service password-encryption
banner motd #Unauthorized access...# 
vlan 2
name Bikes
vlan 3
name Trikes
vlan 4
name Management
vlan 5 
name Parking
vlan 6
name Native
interface range f0/1 - 2, f0/5 
switchport mode trunk
switchport trunk native vlan 6
channel-group 1 mode lacp 
interface range f0/1 - 2 
channel-group 1 mode lacp
interface f0/6
switchport access vlan 2
switchport mode access
switchport port-security maximum 3 
switchport port-security
interface range f0/3 - 4, f0/7 - 24 
description ***Shutdown***
switchport access vlan 5 
switchport mode access
shutdown
interface vlan 4
description Management Interface
ip address 10.19.8.98 255.255.255.224 
ipv6 address 2001:db8:acad:c::98/64
ipv6 enable
no shutdown
ip default-gateway 10.19.8.97
crypto key generate rsa
Type in 1024 
end
copy running-config startup-config 

-------------------------------------------------------------
## switch TWO

### c copy and paste for switch 2 

configure terminal 
no ip domain-lookup 
hostname S2
ip domain-name ccna-lab.com
enable secret ciscoenpass 
line console 0
password ciscoconpass
login
exit
line vty 0 15
password ciscoconpass
login local
transport input ssh
exit 
service password-encryption
banner motd #Unauthorized access...# 
vlan 2
name Bikes
vlan 3
name Trikes
vlan 4
name Management
vlan 5 
name Parking
vlan 6
name Native
interface range f0/1 - 2, f0/5 
switchport mode trunk
switchport trunk native vlan 6
channel-group 1 mode lacp 
interface range f0/1 - 2 
channel-group 1 mode lacp
interface f0/18 
switchport access vlan 3
switchport mode access
switchport port-security maximum 3 
switchport port-security
interface range f0/3 - 4, f0/7 - 24 
description ***Shutdown***
switchport access vlan 5 
switchport mode access
shutdown
interface vlan 4
description Management Interface
ip address 10.19.8.99 255.255.255.224 
ipv6 address 2001:db8:acad:c::99/64
ipv6 enable
no shutdown
ip default-gateway 10.19.8.97
crypto key generate rsa
type in 1024 
end
copy running-config startup-config

-------------------------------------------------------------
## Router

Router> enable
Router# configure terminal
Router(config)# no ip domain-lookup 
Router(config)# hostname R1
Router(config)# ip domain-name ccna-lab.com
Router(config)# enable secret ciscoenpass 
Router(config)# line console 0
Router(config-line)# password ciscoconpass
Router(config-line)# login
Router(config-line)# exit
Router(config)# line vty 0 15
Router(config-line)# password ciscoconpass
Router(config-line)# login local
Router(config-line)# transport input ssh
Router(config-line)# exit 
Router(config)# service password-encryption
Router(config)# banner motd #Unauthorized access...# 
Router(config)# ip routing  
Router(config)# interface G0/0/1
Router(config-if)# description Link to Switch S1 
Router(config-if)# ip address 10.19.8.1 255.255.255.192
Router(config-if)# ipv6 address 2001:db8:acad:a::1/64
Router(config-if)# ipv6 enable 
Router(config-if)# no shutdown 
Router(config-if)# exit 
Router(config)# interface G0/0/1.2 
Router(config-if)# description VLAN 2 
Router(config-if)# encapsulation dot1q 2
Router(config-if)# ip address 10.19.8.1 255.255.255.192
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface G0/0/1.3 
Router(config-if)# description VLAN 3 
Router(config-if)# encapsulation dot1q 3
Router(config-if)# ip address 10.19.8.65 255.255.255.192
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface G0/0/1.4 
Router(config-if)# description VLAN 4
Router(config-if)# encapsulation dot1q 4
Router(config-if)# ip address 10.19.8.97 255.255.255.224
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface Loopback0
Router(config-if)# description Management Interface
Router(config-if)# ip address 209.165.201.1 255.255.255.224
Router(config-if)# ipv6 address 2001:db8:acad:209::1/64
Router(config-if)# ipv6 enable 
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# crypto key generate rsa 
1024

here is the same thing with everything for the router (copy and paste)

### copy and paste for the router

 enable
 configure terminal
 no ip domain-lookup 
 hostname R1
 ip domain-name ccna-lab.com
 enable secret ciscoenpass 
 line console 0
 password ciscoconpass
 login
 exit
line vty 0 15
 password ciscoconpass
 login local
 transport input ssh
 exit 
 service password-encryption
 banner motd #Unauthorized access...# 
 ip routing  
 interface G0/0/1
 description Link to Switch S1 
 ip address 10.19.8.1 255.255.255.192
 ipv6 address 2001:db8:acad:a::1/64
 ipv6 enable 
 no shutdown 
 exit 
interface G0/0/1.2 
 description VLAN 2 
 encapsulation dot1q 2
 ip address 10.19.8.1 255.255.255.192
 no shutdown
 exit
interface G0/0/1.3 
description VLAN 3 
encapsulation dot1q 3
ip address 10.19.8.65 255.255.255.192
no shutdown
exit
interface G0/0/1.4 
 description VLAN 4
 encapsulation dot1q 4
 ip address 10.19.8.97 255.255.255.224
 no shutdown
 exit
interface Loopback0
 description Management Interface
 ip address 209.165.201.1 255.255.255.224
 ipv6 address 2001:db8:acad:209::1/64
 ipv6 enable 
 no shutdown
 exit
crypto key generate rsa 
(Enter 1024 into the command line) 
end