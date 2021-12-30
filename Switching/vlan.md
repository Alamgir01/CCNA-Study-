
![vlan](https://user-images.githubusercontent.com/20280030/147767878-3225334b-3d48-4f75-806e-cdc65a13d4f8.png)


create vlan  in Switch 1 
================================================================
Switch>enable

Switch#configure terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit


assigning port to vlan in Switch 1 
=================================================================
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


Making port trunk for passing traffic in switch 1 
===================================================================== 
Switch(config)#interface range fastEthernet 0/7

Switch(config-if-range)#switchport mode trunk 				
			
			
create vlan  in Switch 2
======================================================================
Switch>enable

Switch#configure terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit


assigning port to vlan in Switch 2
=========================================================================
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


Making port trunk for passing traffic in switch 2 
======================================================================== 
Switch(config)#interface range fastEthernet 0/7-8

Switch(config-if-range)#switchport mode trunk 				
			
			
create vlan  in Switch 3
=========================================================================
Switch>enable

Switch#configure terminal 

Switch(config)#vlan 10

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit


assigning port to vlan in Switch 3 
==========================================================================
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


Making port trunk for passing traffic in switch 3 
=========================================================================== 
Switch(config)#interface  fastEthernet 0/7

Switch(config-if-range)#switchport mode trunk 


End 
===========================================================================
