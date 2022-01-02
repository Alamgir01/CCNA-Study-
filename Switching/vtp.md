
![vtp](https://user-images.githubusercontent.com/20280030/147866111-d366e835-29fc-4299-bcd5-f2b4ad12fc86.png)

vlan trunk protocol  vtp
===============================================

Give these command to switch server 
------------------------------------------------

Switch>enable 

Switch#configure terminal 

Switch(config)#vtp mode server 

Switch(config)#vtp domain cisco

Switch(config)#vtp password cisco123

Switch(config)#exit

Create vlans 
-------------------------------------------------

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30

Switch(config-vlan)#name HR

Switch(config-vlan)#exit


Give these command to switch transparent
--------------------------------------------------

Switch>enable 

Switch#configure terminal 

Switch(config)#vtp mode transparent 

Switch(config)#vtp domain cisco

Switch(config)#vtp password cisco123

Switch(config)#exit

Make trunk ports 
---------------------------------------------------

Switch(config)#interface range fastEthernet 0/1-4

Switch(config-if-range)#switchport mode trunk

Switch(config-if-range)#exit


Give these command to switch client 
----------------------------------------------------

Switch>enable

Switch#configure terminal

Switch(config)#vtp mode client 

Switch(config)#vtp domain cisco

Switch(config)#vtp password cisco123

Switch(config)#exit

Switch(config)#interface range fastEthernet 0/1-3

Switch(config-if-range)#switchport mode access

Switch(config-if-range)#exit

Switch(config)#interface fastEthernet 0/1

Switch(config-if)#switchport access vlan 10

Switch(config-if)#exit

Switch(config)#interface fastEthernet 0/2
Switch(config-if)#switchport access vlan 20
Switch(config-if)#exit


Switch(config)#interface fastEthernet 0/3

Switch(config-if)#switchport access vlan 30

Switch(config-if)#exit

End
--------------------------------------------------------------------------------------------------
