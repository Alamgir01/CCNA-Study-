

![ether channel](https://user-images.githubusercontent.com/20280030/147866191-cc07e2dd-a596-4fc2-8c97-a09645b73d64.png)
![Ether cahnnle](https://user-images.githubusercontent.com/20280030/147866190-ce7873b8-4435-476d-b6a9-20e7d0e68556.png)





Ether channel using PagP
======================================================

In switch 1

Switch>enable

Switch#configure terminal 

Switch(config)#interface range fastEthernet 0/1-3

Switch(config-if-range)#channel-protocol pagp 

Switch(config-if-range)#channel-group 1 mode desirable 

Switch(config-if-range)#exit

In switch 2 

Switch>enable

Switch#configure terminal 

Switch(config)#interface range fastEthernet 0/1-3

Switch(config-if-range)#channel-protocol pagp 

Switch(config-if-range)#channel-group 1 mode desirable 

Switch(config-if-range)#exit


Ether channel using Lacp
======================================================

Give these command in two switches 

Switch>enable 

Switch#configure terminal 

Switch(config)#interface range fastEthernet 0/1-3

Switch(config-if-range)#channel-protocol lacp 

Switch(config-if-range)#channel-group 2 mode active 

Switch(config-if-range)#exit


End 
-------------------------------------------------------------
