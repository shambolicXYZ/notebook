set firewall family inet filter control-plane term OSPF from protocol ospf
set firewall family inet filter control-plane term OSPF from interface-set internal
set firewall family inet filter control-plane term OSPF then accept
set firewall family inet filter control-plane term LDP from port ldp
set firewall family inet filter control-plane term LDP from interface-set internal
set firewall family inet filter control-plane term LDP then accept
set firewall family inet filter control-plane term BGP from source-prefix-list BGP-peers
set firewall family inet filter control-plane term BGP from protocol tcp
set firewall family inet filter control-plane term BGP from port bgp
set firewall family inet filter control-plane term BGP then accept
set firewall family inet filter control-plane term VRRP from protocol vrrp
set firewall family inet filter control-plane term VRRP then accept
set firewall family inet filter control-plane term ICMP from protocol icmp
set firewall family inet filter control-plane term ICMP then policer ICMP-6m
set firewall family inet filter control-plane term ICMP then accept
set firewall family inet filter control-plane term UDP-Traceroute from protocol udp
set firewall family inet filter control-plane term UDP-Traceroute from port 33434-33534
set firewall family inet filter control-plane term UDP-Traceroute then policer UDP-Traceroute-256k
set firewall family inet filter control-plane term UDP-Traceroute then accept
set firewall family inet filter control-plane term mgmt from source-prefix-list MZ-segments
set firewall family inet filter control-plane term mgmt from source-prefix-list Transits
set firewall family inet filter control-plane term mgmt from interface-set internal
set firewall family inet filter control-plane term mgmt then accept
set firewall family inet filter control-plane term outbound-mgmt from protocol tcp
set firewall family inet filter control-plane term outbound-mgmt from source-port telnet
set firewall family inet filter control-plane term outbound-mgmt from source-port ssh
set firewall family inet filter control-plane term outbound-mgmt from tcp-established
set firewall family inet filter control-plane term outbound-mgmt then accept
set firewall family inet filter control-plane term local-traffic from source-address 127.0.0.1
set firewall family inet filter control-plane term local-traffic from source-address 172.16.128.27
set firewall family inet filter control-plane term local-traffic then accept
set firewall family inet filter control-plane term services from port ntp
set firewall family inet filter control-plane term services from port domain
set firewall family inet filter control-plane term services from port radius
set firewall family inet filter control-plane term services from interface-set internal
set firewall family inet filter control-plane term services then accept
set firewall family inet filter control-plane term deny-other then count control-plane-denied
set firewall family inet filter control-plane term deny-other then discard
set firewall policer UDP-Traceroute-256k if-exceeding bandwidth-limit 256k
set firewall policer UDP-Traceroute-256k if-exceeding burst-size-limit 4k
set firewall policer UDP-Traceroute-256k then discard
set firewall policer ICMP-6m if-exceeding bandwidth-limit 6m
set firewall policer ICMP-6m if-exceeding burst-size-limit 64k
set firewall policer ICMP-6m then discard