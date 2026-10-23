## SSH 

-- Pre-configured hostname before using this --

ip domain-name TNARC.com
crypto key generate rsa
2048
ip ssh version 2
line vty 0 15
transport input ssh

## AAA Server

service password-encryption
username localadmin secret localpass
enable secret CiscoTNARCtest
tacacs-server host 10.0.201.10
tacacs-server key tacacskey
aaa new-model
aaa authentication login default group tacacs+ local
line console 0
login authentication default
exit
line vty 0 15
login authentication default
exit

## DHCP Snooping

ip dhcp snooping
ip dhcp snooping vlan 10,20,30,99
no ip dhcp snooping information option
int range g0/1-2
ip dhcp snooping trust
exit
do write
 

ip dhcp snooping
ip dhcp snooping vlan 110,120,130,199
no ip dhcp snooping information option
int range g0/1-2
ip dhcp snooping trust
exit
do write
 

## Dynamic ARP Inspection

ip arp inspection vlan 110,120
ip arp inspection validate src-mac dst-mac ip
int range g0/1-2
ip arp inspection trust
exit
do write

ip arp inspection vlan 130,199
ip arp inspection validate src-mac dst-mac ip
int range g0/1-2
ip arp inspection trust
exit
do write

ip arp inspection vlan 10,20
ip arp inspection validate src-mac dst-mac ip
int range g0/1-2
ip arp inspection trust
exit
do write

ip arp inspection vlan 30,99
ip arp inspection validate src-mac dst-mac ip
int range g0/1-2
ip arp inspection trust
exit
do write

## Port-security

int range f0/1-4
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
switchport port-security violation shutdown
exit

## Portfast and BPDUguard

spanning-tree portfast bpduguard default

## SSH VTY ACL

ip access-list extended SSH_Management
permit tcp 10.0.99.0 0.0.0.255 any eq 22
permit tcp 10.0.199.9 0.0.0.255 any eq 22
line vty 0 15
access-class SSH_Management in
exit

## VTY exec-timeout and SSH login limit and timeout

ip ssh authentication-retries 3
ip ssh time-out 60
line console 0
exec-timeout 5 0
line vty 0 15
exec-timeout 5 0
exit

## Banner

banner motd z
WARNING! Access is restricted and monitored. z