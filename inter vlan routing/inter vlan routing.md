![intra vlan](https://user-images.githubusercontent.com/20280030/147723883-de414dc2-5f67-4c43-9c31-3640d76b9ca8.png)



SWITCH 1
==========================================================
Switch>enable 
Switch#configure  terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-6

Switch(config-if-range)#switchport mode access

Switch(config-if-range)#interface range fastEthernet 0/1-2

Switch(config-if-range)#switchport access vlan 10

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/3-4

Switch(config-if-range)#switchport access vlan 20 

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/5-6

Switch(config-if-range)#switchport access vlan 30 

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/7-8

Switch(config-if-range)#switchport mode trunk 


SWITCH 2 
==========================================================
Switch>enable 

Switch#configure  terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-6

Switch(config-if-range)#switchport mode access

Switch(config-if-range)#interface range fastEthernet 0/1-2

Switch(config-if-range)#switchport access vlan 10

Switch(config-if-range)#exit


Switch(config)#interface range fastEthernet 0/3-4

Switch(config-if-range)#switchport access vlan 20 

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/5-6

Switch(config-if-range)#switchport access vlan 30 

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/7-8

Switch(config-if-range)#switchport mode trunk 


SWITCH 3
==========================================================
Switch>enable 

Switch#configure  terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-6

Switch(config-if-range)#switchport mode access

Switch(config-if-range)#interface range fastEthernet 0/1-2

Switch(config-if-range)#switchport access vlan 10

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/3-4

Switch(config-if-range)#switchport access vlan 20 

Switch(config-if-range)#exit

Switch(config)#interface range fastEthernet 0/5-6

Switch(config-if-range)#switchport access vlan 30 

Switch(config-if-range)#exit 

Switch(config)#interface fastEthernet 0/7

Switch(config-if)#switchport mode trunk 


Router configuration
============================================================ 
Router>enable 

Router#configure terminal 

Router(config)#interface fastEthernet 0/0

Router(config-if)#no shutdown 

Router(config-if)#exit

Router(config)#interface fastEthernet 0/0.10

Router(config-subif)#ip address 10.0.0.1 255.255.255.0 

Router(config-subif)#encapsulation dot1Q 10

Router(config-subif)#exit

Router(config)#interface fastEthernet 0/0.20

Router(config-subif)#ip address 20.0.0.1 255.255.255.0 

Router(config-subif)#encapsulation dot1Q 20

Router(config-subif)#exit

Router(config)#interface fastEthernet 0/0.30

Router(config-subif)#ip address 30.0.0.1 255.255.255.0 

Router(config-subif)#encapsulation dot1Q 30

Router(config-subif)#exit


Creating dhcp pool
==============================================================
Router(config)#ip dhcp pool vlan_10

Router(dhcp-config)#network 10.0.0.0 255.255.255.0

Router(dhcp-config)#default-router 10.0.0.1 

Router(config)#ip dhcp pool vlan_20

Router(dhcp-config)#network 20.0.0.0 255.255.255.0

Router(dhcp-config)#default-router 20.0.0.1 

Router(dhcp-config)#ip dhcp pool vlan30

Router(dhcp-config)#network 30.0.0.0 255.255.255.0

Router(dhcp-config)#default-router 30.0.0.1 


END
==============================================================
