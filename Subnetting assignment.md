@c1
conf t
vlan 23
name fuelsave.com
Interface vlan 23
 desc fuelsave.com
 no shut
 ip add 10.0.2.1 255.255.254.0
ip dhcp excluded-add 10.0.2.1 255.255.254.0
ip dhcp pool fuelsave.com
 network 10.0.16.0 255.255.240.0
 default-router 10.0.2.1
domain-name fuelsave.com

!@c2
int e1/0
no shut
switchport mode access
switchport access vlan 23
do sh vlan brief



@s2 conf t
int e1/0
no shut
ip add dhcp
do bp
