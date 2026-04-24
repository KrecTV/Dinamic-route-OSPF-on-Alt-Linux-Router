# Dinamic-route-OSPF-on-Alt-Linux-Router


apt-get install -y frr

nano /etc/frr/daemons

ospfd=yes

systemctl enable --now frr.service

vtysh

conf t

router ospf

passive-interface default

network 192.168.100.0/29 area 0

network 192.168.200.0/24 area 0

network 192.168.99.0/29 area 0

network 192.168.255.0/30 area 0

exit

interface gre1

no ip ospf passive

ip ospf authentication-key 1234

end

wr mem

exit
