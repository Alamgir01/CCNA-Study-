

![static default routing](https://user-images.githubusercontent.com/20280030/147900489-131f188d-a08d-4faa-a96a-184d5fd63f2d.png)


Static and Default routing 
---------------------------------------------------------------------------

Router 0
---------------------------------------------------------------------------
outer>enable

Router#configure terminal

Router(config)#interface fastEthernet 0/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 192.168.0.1 255.255.255.0

Router(config-if)#exit


Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 172.16.0.1 255.255.255.252

Router(config-if)#exit


configure static routing
---------------------------------------------------------
Router(config)#ip route 10.0.1.0 255.255.255.252  serial 2/0

Router(config)#ip route 100.0.0.0 255.255.255.252 serial 2/0


configure default routing
---------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 se2/0





Router 1 
---------------------------------------------------------------------------
Router>enable 

Router#configure terminal 

Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 172.16.0.2 255.255.255.252

Router(config-if)#exit


Router(config)#interface serial 3/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 10.0.1.1 255.255.255.252

Router(config-if)#exit


configure static routing
---------------------------------------------------------
Router(config)#ip route 192.168.0.0 255.255.255.0 serial 2/0 

Router(config)#ip route 100.0.0.0 255.255.255.252 serial 3/0


configure default routing
---------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 se3/0




R2
----------------------------------------------------------------------------------
Router>enable 

Router#configure terminal 

Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 10.0.1.2 255.255.255.252 

Router(config-if)#exit


Router(config)#interface serial 3/0
 
Router(config-if)#ip address 100.0.0.1 255.255.255.252 

Router(config-if)#exit


configure static routing
------------------------------------------------------------------------
Router(config)#ip route 172.16.1.0 255.255.255.252 serial 2/0

Router(config)#ip route 192.168.0.0 255.255.255.0 serial 2/0


configure default routing
------------------------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 serial 3/0



R3
--------------------------------------------------------------------------
Router>enable 

Router#configure terminal 

Router(config)#interface serial 3/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 100.0.0.2 255.255.255.252 

Router(config-if)#exit


Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 10.0.0.1 255.255.255.252 

Router(config-if)#exit



configure static routing
-------------------------------------------------------------------------
Router(config)#ip route 172.16.0.0 255.255.255.252 serial 2/0 

Router(config)#ip route 192.168.1.0 255.255.255.0 serial 2/0 

configure default routing
-------------------------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 se 2/0 



R4
-------------------------------------------------------------------------
Router>enable 

Router#configure terminal 

Router(config)#interface serial 3/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 10.0.0.2 255.255.255.252 

Router(config-if)#exit


Router(config)#interface serial 2/0 

Router(config-if)#no shutdown 

Router(config-if)#ip address 172.16.0.1 255.255.255.252 

Router(config-if)#exit


configure static routing
---------------------------------------------------------
Router(config)#ip route 192.168.1.0 255.255.255.0 serial 2/0

Router(config)#ip route 100.0.0.0 255.255.255.252 serial 3/0

configure default routing
---------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 se 3/0



R5
-------------------------------------------------------------------------------
Router>enable

Router#configure terminal 

Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 172.16.0.2 255.255.255.252 

Router(config-if)#exit


Router(config)#interface fastEthernet 0/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 192.168.1.1 255.255.255.0 

Router(config-if)#exit


configure static routing
---------------------------------------------------------------
Router(config)#ip route 10.0.0.0 255.255.255.252 serial 2/0

Router(config)#ip route 100.0.0.0 255.255.255.252 serial 2/0

configure default routing
-------------------------------------------------------------------
Router(config)#ip route 0.0.0.0 0.0.0.0 se 2/0 




End 
-------------------------------------------------------------------------------
