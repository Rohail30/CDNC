# Router
Router>
Router>ena
Router>enable 
Router#hostname R
                ^
% Invalid input detected at '^' marker.
	
Router#hostname R
                ^
% Invalid input detected at '^' marker.
	
Router#config
Router#configure t
Router#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#hostname R
R(config)#int g0/0
R(config-if)#ip address 192.168.1.1 255.255.255.0
R(config-if)#des
R(config-if)#description conn
R(config-if)#description connected to zabdesk
R(config-if)#no shut

R(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

R(config-if)#end
R#
%SYS-5-CONFIG_I: Configured from console by console


R#service dhcp pool zabdesk
          ^
% Invalid input detected at '^' marker.
	
R#service dhcp 
          ^
% Invalid input detected at '^' marker.
	
R#conf
R#configure t
R#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
R(config)#service dhcp
R(config)#ip dhcp pool ZABDESK
R(dhcp-config)#network 192168.1.0 255.255.255.0
                       ^
% Invalid input detected at '^' marker.
	
R(dhcp-config)#default
R(dhcp-config)#default-router 192.168.1.1
R(dhcp-config)#dns
R(dhcp-config)#dns-server 8.8.8.8
R(dhcp-config)#exit
R(config)#ip dhc
R(config)#ip dhcp exclu
R(config)#ip dhcp excluded-address from
R(config)#ip dhcp excluded-address from c
R(config)#ip dhcp excluded-address from cons
R(config)#ip dhcp excluded-address 192.168.1.1 192.168.1.2
R(config)#exit
R#
%SYS-5-CONFIG_I: Configured from console by console

R#cof
R#con
R#con
R#conf
R#configure t
R#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
R(config)#line vty 0 15
R(config-line)#cisco
               ^
% Invalid input detected at '^' marker.
	
R(config-line)#password cisco
R(config-line)#login
R(config-line)#exit
R(config)#copy run config
            ^
% Invalid input detected at '^' marker.
	
R(config)#co
R(config)#exit
R#
%SYS-5-CONFIG_I: Configured from console by console

R#cop
R#copy r
R#copy running-config 
% Incomplete command.





# swith

Switch>
Switch>
Switch>
Switch>
Switch>
Switch>en
Switch>enable 
Switch#co
Switch#conf
Switch#configure t
Switch#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#hostname S1
S1(config)#interface vlan 1
S1(config-if)#ip ad
S1(config-if)#ip address 192.168.1.2 255.255.255.0
S1(config-if)#no shut

S1(config-if)#
%LINK-5-CHANGED: Interface Vlan1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan1, changed state to up

S1(config-if)#exit
S1(config)#de
S1(config)#default-g
S1(config)#default-gat
S1(config)#ip d
S1(config)#ip default-ga
S1(config)#ip default-gateway 192.168.1.1
S1(config)#line vty 0 15
S1(config-line)#pas
S1(config-line)#password cisco
S1(config-line)#log
S1(config-line)#log
% Ambiguous command: "log"
S1(config-line)#login
S1(config-line)#end
S1#
%SYS-5-CONFIG_I: Configured from console by console

S1#copy r
S1#copy running-config 
% Incomplete command.

