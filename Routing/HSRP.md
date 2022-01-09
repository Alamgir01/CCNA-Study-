

![HSRP](https://user-images.githubusercontent.com/20280030/148684028-af2c813f-6a17-4e9b-bbfd-166583e61daa.png)

High Availability (HSRP)
------------------------------------------------------
in pc use 192.168.0.100 as default getway 


router 0
-------------------------------------------------------
Router>enable

Router#configure terminal 

Router(config)#interface fastEthernet 0/0

Router(config-if)#ip address 192.168.0.1 255.255.255.0

Router(config-if)#exit 



HSRP  configuration
-------------------------------------------------------
Router(config)#interface fastEthernet 0/0

Router(config-if)#standby 10 ip 192.168.0.100 

Router(config-if)#exit



router 1
------------------------------------------------------
Router>enable

Router#configure terminal 

Router(config)#interface fastEthernet 0/0

Router(config-if)#ip address 192.168.0.2 255.255.255.0

Router(config-if)#exit 



HSRP configuration
-------------------------------------------------------

Router(config)#interface fastEthernet 0/0

Router(config-if)#standby 10 ip 192.168.0.100

Router(config-if)#exit


router 2
--------------------------------------------------------
Router>enable

Router#configure terminal 

Router(config-if)#ip address 192.168.0.3 255.255.255.0 

Router(config-if)#exit

HSRP configuration
--------------------------------------------------------
Router(config)#interface fastEthernet 0/0

Router(config-if)#standby 10 ip 192.168.0.100

Router(config-if)#exit


END
-------------------------------------------------------
