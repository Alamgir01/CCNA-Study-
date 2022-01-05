![dhcp server](https://user-images.githubusercontent.com/20280030/148160262-f6cf180f-cec1-4378-bfef-ca3cab22fb4a.png)



DHCP configuration 
===================================================
Here i will create 4 dhcp pool  

Assign ip to the interfaces
---------------------------------------------------


Router>enable 

Router(config)#interface fastEthernet 0/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 150.0.0.1 255.255.255.0

Router(config-if)#exit

Router(config)#interface fastEthernet 2/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 100.0.0.1 255.255.255.0

Router(config-if)#exit

Router(config)#interface fastEthernet 1/0

Router(config-if)#no shutdown

Router(config-if)#ip address 50.0.0.1 255.255.255.0

Router(config-if)#exit

Router(config)#interface fastEthernet 3/0

Router(config-if)#no shutdown 

Router(config-if)#ip address 200.0.0.1 255.255.255.0 

Router(config-if)#exit


Creating dhcp pool
-----------------------------------------------------------------------------

Router(config)#ip dhcp pool pool_1

Router(dhcp-config)#network 150.0.0.0 255.255.255.0 

Router(dhcp-config)#default-router 150.0.0.1

Router(dhcp-config)#exit


Router(config)#ip dhcp pool pool_2

Router(dhcp-config)#network 100.0.0.0 255.255.255.0

Router(dhcp-config)#default-router 100.0.0.1 

Router(dhcp-config)#exit

Router(config)#ip dhcp pool pool_3

Router(dhcp-config)#network 50.0.0.0 255.255.255.0 

Router(dhcp-config)#default-router 50.0.0.1 

Router(dhcp-config)#exit

Router(config)#ip dhcp pool pool_4

Router(dhcp-config)#network 200.0.0.0 255.255.255.0 

Router(dhcp-config)#default-router 200.0.0.1

Router(dhcp-config)#exit



END
----------------------------------------------------------
