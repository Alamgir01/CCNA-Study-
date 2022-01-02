![port security](https://user-images.githubusercontent.com/20280030/147866295-3c04e4d4-a4eb-4c73-9eb1-b2e820ba1087.png)



In port 0/1 only this mac 0060.47ED.5239 will work  security violence restrict
-------------------------------------------------------------------------------
Switch>enable 

Switch#configure terminal 

Switch(config)#interface fa0/1

Switch(config-if)#switchport mode access 

Switch(config-if)#switchport port-security 

Switch(config-if)#switchport port-security mac-address 0060.47ED.5239

Switch(config-if)#switchport port-security violation restrict 


In port 0/2 only 2 device can work   mac address sticky      security violence protect
----------------------------------------------------------------------------------------
Switch(config)#interface fa0/2

Switch(config-if)#switchport mode access

Switch(config-if)#switchport port-security 

Switch(config-if)#switchport port-security violation protect 

Switch(config-if)#switchport port-security maximum 2 

Switch(config-if)#switchport port-security mac-address sticky 

End 
----------------------------------------------------------------------------------------
