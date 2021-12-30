![pvstp](https://user-images.githubusercontent.com/20280030/147768475-5e499517-424e-4151-8961-51a6b802b11e.png)





Per-vlan Spanning tree protocol pvst
=========================================================

Switch 1 
=========================================================
Note : create all these vlan in every switch  

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface fastEthernet 0/1-3

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

Switch(config)#interface range fastEthernet 0/4-5

Switch(config-if-range)#switchport mode trunk  

Switch(config)#spanning-tree mode pvst 



Switch 2
=========================================================

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface fastEthernet 0/1-3

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

Switch(config)#interface range fastEthernet 0/4-5

Switch(config-if-range)#switchport mode trunk  

Switch(config)#spanning-tree mode pvst 


Switch 3 
=========================================================

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-4

Switch(config-if-range)#switchport mode trunk 

Switch(config)#spanning-tree mode pvst 


Switch 4 
=========================================================

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-4

Switch(config-if-range)#switchport mode trunk 

Switch(config)#spanning-tree mode pvst 


Switch 5 
=========================================================

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-2

Switch(config-if-range)#switchport mode trunk 

enable pvst
---------------------------------------------------------
Switch(config)#spanning-tree mode pvst 

Switch(config)#spanning-tree vlan 20 root primary 

Switch(config)#spanning-tree vlan 30 root primary

Switch(config)#spanning-tree vlan 10 root secondary 

Switch(config)#exit


Switch 6 
=========================================================

Switch>enable

Switch#configur terminal 

Switch(config)#vlan 10 

Switch(config-vlan)#name IT

Switch(config-vlan)#vlan 20 

Switch(config-vlan)#name AC

Switch(config-vlan)#vlan 30 

Switch(config-vlan)#name HR

Switch(config-vlan)#exit

Switch(config)#interface range fastEthernet 0/1-2
Switch(config-if-range)#switchport mode trunk 

enable pvst
---------------------------------------------------------
Switch(config)#spanning-tree mode pvst

Switch(config)#spanning-tree vlan 10 root primary 

Switch(config)#spanning-tree vlan 20 root secondary 

Switch(config)#spanning-tree vlan 30 root secondary 

Switch(config)#exit



END
==========================================================
