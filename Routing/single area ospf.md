![single area ospf](https://user-images.githubusercontent.com/20280030/148159883-468af805-e2a6-4b3d-ac3b-44187fcd0146.png)



Single area ospf
-------------------------------------------------------------
Here i will configure sigle area ospf 


router 0 
---------------------------------------------------------
Router>enable 
Router#configure terminal
Router(config)#interface fastEthernet 0/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 10.0.0.1 255.255.255.0
Router(config-if)#exit

Router(config)#interface serial 2/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 100.0.0.1 255.255.255.252 
Router(config-if)#exit

Router(config-if)#interface serial 3/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 200.0.0.1 255.255.255.252 
Router(config-if)#exit

configuring ospf
--------------------------------------------------------------------
Router(config)#router ospf 10
Router(config-router)#network 10.0.0.1 0.0.0.0 area 0  
Router(config-router)#network 100.0.0.1 0.0.0.0 area 0 
Router(config-router)#network 200.0.0.1 0.0.0.0 area 0 





router 1 
-----------------------------------------------------------------
Router>enable
Router#configure terminal
Router(config)#interface fastEthernet 0/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 172.16.0.1 255.255.255.0
Router(config-if)#exit

Router(config)#interface serial 2/0
Router(config-if)#no shutdown
Router(config-if)#ip address 100.0.0.2 255.255.255.252
Router(config-if)#exit 

Router(config)#interface serial 3/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 200.100.0.1 255.255.255.252
Router(config-if)#exit

configuring ospf
--------------------------------------------------------------------
Router(config)#router ospf 10
Router(config-router)#network 172.16.0.1 0.0.0.0 area 0
Router(config-router)#network 100.0.0.2 0.0.0.0 area 0
Router(config-router)#network 200.100.0.1 0.0.0.0 area 0
Router(config-router)#exit






router 2
----------------------------------------------------------------------
Router>enable 
Router#configure terminal
Router(config)#interface fastEthernet 0/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 10.10.0.1 255.255.255.0
Router(config-if)#exit

Router(config)#interface serial 3/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 200.100.0.2 255.255.255.252 
Router(config-if)#exit

Router(config)#interface serial 2/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 100.100.0.1 255.255.255.252 
Router(config-if)#exit

configuring ospf
--------------------------------------------------------------------
Router(config)#router ospf 10
Router(config-router)#network 200.100.0.2 0.0.0.0 area 0
Router(config-router)#network 100.100.0.1 0.0.0.0 area 0
Router(config-router)#network 10.10.0.1 0.0.0.0 area 0
Router(config-router)#exit







router 3 
------------------------------------------------------------------
Router>enable
Router#configure terminal
Router(config)#interface fastEthernet 0/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 192.168.0.1 255.255.255.0 
Router(config-if)#exit

Router(config)#interface serial 3/0
Router(config-if)#no shutdown 
Router(config-if)#ip address 200.0.0.2 255.255.255.252 
Router(config-if)#exit 

Router(config)#interface serial 2/0
Router(config-if)#no shutdown
Router(config-if)#ip address 100.100.0.2 255.255.255.252 
Router(config-if)#exit

configuring ospf
--------------------------------------------------------------------
Router(config)#router ospf 10
Router(config-router)#network 192.168.0.1 0.0.0.0 area 0
Router(config-router)#network 100.100.0.2 0.0.0.0 area 0
Router(config-router)#network 200.0.0.2 0.0.0.0 area 0
Router(config-router)#exit



END
--------------------------------------------------------------------
