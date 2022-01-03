

![static default routing](https://user-images.githubusercontent.com/20280030/147903112-bc7ec86e-1f51-41e8-b6c3-ac406c70100f.png)



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

Router(config-if)#ip address 172.16.1.1 255.255.255.252

Router(config-if)#exit


configure RIP routing
---------------------------------------------------------------------------
Router(config)#router rip

Router(config-router)#version 2

Router(config-router)#network 192.168.0.0 

Router(config-router)#network 172.16.1.0



Router 1 
---------------------------------------------------------------------------
Router>enable 

Router#configure terminal 

Router(config)#interface serial 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 172.16.1.2 255.255.255.252

Router(config-if)#exit


Router(config)#interface serial 3/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 10.0.1.1 255.255.255.252

Router(config-if)#exit


configure RIP routing
---------------------------------------------------------
Router(config)#route rip

Router(config-router)#version 2

Router(config-router)#network 172.16.1.0

Router(config-router)#network 10.0.1.0

Router(config-router)#exit



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


configure RIP routing
------------------------------------------------------------------------
Router(config)#route rip

Router(config-router)#version 2

Router(config-router)#network 10.0.1.0 

Router(config-router)#network 100.0.0.0


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



configure RIP routing
-------------------------------------------------------------------------
Router(config)#router rip

Router(config-router)#version

Router(config-router)#network 100.0.0.0 

Router(config-router)#network 10.0.0.0 


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


configure RIP routing
---------------------------------------------------------
Router(config)#router rip

Router(config-router)#version 2 

Router(config-router)#network 10.0.0.0 

Router(config-router)#network 172.16.0.0


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


configure RIP routing
---------------------------------------------------------------
Router(config-router)#route rip 

Router(config-router)#version 2

Router(config-router)#network 172.16.0.0 

Router(config-router)#network 192.168.1.0




End 
-------------------------------------------------------------------------------
