![multi area ospf](https://user-images.githubusercontent.com/20280030/148569030-871093d2-12c9-4db8-85fe-dc44185db95b.png)






Multi area ospf 
-----------------------------------------------




router 1.1.1.1
----------------------------------------------
enable

configure terminal

hostname 1.1.1.1

interface se 2/0

no shutdown

ip address 100.0.0.1 255.255.255.252 

exit

interface se 3/0

no shutdown

ip address 100.0.2.1 255.255.255.252

exit


ospf configuration
--------------------------------------------------------
route ospf 100

network 100.0.0.1 0.0.0.0 area 0

network 100.0.2.1 0.0.0.0 area 0

router-id 1.1.1.1

exit



router 2.2.2.2
----------------------------------------------
enable

configure terminal

hostname 2.2.2.2

interface se2/0

no shutdown

ip address 100.0.1.2 255.255.255.252

exit

interface se3/0

no shutdown 

ip address 100.0.2.2 255.255.255.252 

exit

interface se 6/0

no shutdown 

ip address 100.10.0.1 255.255.255.252

exit



ospf configuration
--------------------------------------------------------
	
router ospf 100

network 100.0.2.2 0.0.0.0 area 0

network 100.0.1.2 0.0.0.0 area 0

network 100.10.0.1 0.0.0.0 area 1

router-id 2.2.2.2 

exit


virtual link creation
----------------------------------------------------------
route ospf 100

area 1 virtual-link 5.5.5.5



router 3.3.3.3
----------------------------------------------
enable

configure terminal

hostname 3.3.3.3

interface se2/0

no shutdown

ip address 100.0.0.2 255.255.255.252

exit

interface se3/0

no shutdown

ip address 100.0.1.1 255.255.255.252

exit

ospf configuration
--------------------------------------------------------

router ospf 100

network 100.0.1.1 0.0.0.0 area 0

network 100.0.0.2 0.0.0.0 area 0

router-id 3.3.3.3

exit


router 4.4.4.4
----------------------------------------------------------

enable 

configure terminal

hostname 4.4.4.4

interface se2/0

no shutdown

ip address 100.10.0.2 255.255.255.252

exit

interface se 3/0

no shutdown 

ip address 100.10.1.1 255.255.255.252

exit


ospf configuration
--------------------------------------------------------
router ospf 100

network 100.10.0.2 0.0.0.0 area 1 

network 100.10.1.1 0.0.0.0 area 1 

exit




router 5.5.5.5
------------------------------------------------------------
enable

configure terminal

hostname 5.5.5.5

interface se2/0

no shutdown 

ip address 100.10.1.2 255.255.255.252 

exit

interface se3/0

no shutdown 

ip address 100.20.0.1 255.255.255.252 

exit

ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.10.1.2 0.0.0.0 area 1

network 100.20.0.1 0.0.0.0 area 2

router-id 5.5.5.5

exit

virtual link creation 
----------------------------------------------------------------
router ospf 100

area 1 virtual-link 2.2.2.2

area 2 virtual-link 8.8.8.8


router 6.6.6.6
----------------------------------------------------------
enable

configur terminal 

hostname 6.6.6.6

interface se2/0

no shutdown 

ip address 100.20.0.2 255.255.255.252 

exit

interface se3/0

no shutdown 

ip address 100.20.1.1 255.255.255.252 

exit

ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.20.0.2 0.0.0.0 area 2

network 100.20.1.1 0.0.0.0 area 2

router-id 6.6.6.6

exit


router 7.7.7.7
------------------------------------------------------------
enable 

configure terminal

hostname 7.7.7.7

interface se2/0

no shutdown 

ip address 100.20.1.2 255.255.255.252

exit

interface se3/0

no shutdown 

ip address 100.20.2.1 255.255.255.252

exit


ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.20.1.2 0.0.0.0 area 2

network 100.20.2.1 0.0.0.0 area 2

router-id 7.7.7.7

exit



router 8.8.8.8
-----------------------------------------------------------------
enable

configure terminal 

hostname 8.8.8.8

interface se2/0

no shutdown 

ip address 100.20.2.2 255.255.255.252

exit

interface se3/0

no shutdown 

ip address 100.30.0.1 255.255.255.252 

exit


ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.20.2.2  0.0.0.0 area 2

network 100.30.0.1 0.0.0.0 area 3

router-id 8.8.8.8

exit

virtual link creation
-------------------------------------------------------------------
router ospf 100

area 2 virtual-link  5.5.5.5

area 3 virtual-link  10.10.10.10


router 9.9.9.9
-------------------------------------------------
enable

configure terminal

hostname 9.9.9.9

interface se2/0

no shutdown 

ip address 100.30.0.2 255.255.255.252 

exit

interface se3/0

no shutdown 

ip address 100.30.1.1 255.255.255.252 

exit



ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.30.0.2 0.0.0.0 area 3

network 100.30.1.1 0.0.0.0 area 3

router-id 9.9.9.9

exit




router 10.10.10.10
------------------------------------------------------------

enable

configure terminal

hostname 10.10.10.10

interface se2/0

no shutdown 

ip address 100.30.1.2 255.255.255.252 

exit

interface se3/0

no shutdown 

ip address 100.40.0.1 255.255.255.252

exit


ospf configuration
--------------------------------------------------------------

router ospf 100

network 100.30.1.2 0.0.0.0 area 3

network 100.40.0.1 0.0.0.0 area 4

router-id 10.10.10.10

exit

virtual link creation
---------------------------------------------------------------
router ospf 100

area 3 virtual-link 8.8.8.8

area 4 virtual-link 11.11.11.11





router 11.11.11.11
-------------------------------------------------------------
enable

configure terminal

hostname 11.11.11.11

interface se2/0

no shutdown 

ip address 100.40.0.2 255.255.255.252 

exit

ospf configuration
--------------------------------------------------------------
router ospf 100

network 100.40.0.2 0.0.0.0 area 4

router-id 11.11.11.11

exit

virtual link creation
--------------------------------------------------------------------
router ospf 100

area 4 virtual-link 10.10.10.10 





END
-------------------------------------------------------------------







