set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term discard-and-dont-log-scanner-v4 from source-prefix-list ip-scanners-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term discard-and-dont-log-scanner-v4 then discard
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 from protocol icmp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 from icmp-type echo-request
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 from icmp-type echo-reply
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 from icmp-type unreachable
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 from icmp-type time-exceeded
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-icmp-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ssh-v4 from source-prefix-list management-sources-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ssh-v4 from protocol tcp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ssh-v4 from destination-port 22
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ssh-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-snmp-v4 from source-prefix-list snmp-sources-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-snmp-v4 from protocol tcp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-snmp-v4 from protocol udp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-snmp-v4 from destination-port snmp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-snmp-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ntp-v4 from source-prefix-list ntp-server-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ntp-v4 from source-prefix-list ntp-peer-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ntp-v4 from protocol udp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ntp-v4 from source-port ntp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-ntp-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-local-ntp-queries-v4 from source-prefix-list local-management-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-local-ntp-queries-v4 from destination-prefix-list local-management-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-local-ntp-queries-v4 from protocol udp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-local-ntp-queries-v4 from destination-port ntp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-local-ntp-queries-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-uac-v4 from source-prefix-list uac-servers-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-uac-v4 from protocol tcp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-uac-v4 from source-port 11123
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-uac-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 from source-prefix-list radius-servers-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 from source-prefix-list uac-servers-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 from protocol udp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 from source-port 1812
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 from source-port 1813
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-radius-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 from source-prefix-list name-servers-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 from protocol udp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 from protocol tcp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 from source-port 53
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 from destination-port 1024-65535
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 then count dns-responses-in-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-dns-responses-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-netconf-v4 from source-prefix-list management-sources-v4
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-netconf-v4 from protocol tcp
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-netconf-v4 from destination-port 830
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term accept-netconf-v4 then accept
set groups org-defaults-v1 firewall family inet filter cpp-ipv4-v1 term discard-all-v4 then discard
set groups org-defaults-v1 firewall family inet simple-filter icmp term limit from protocol icmp
set groups org-defaults-v1 firewall family inet simple-filter icmp term limit then policer icmp-4m


set policy-options prefix-list ntp-server-v4 apply-path "system ntp server <*>"
set policy-options prefix-list ntp-peer-v4 apply-path "system ntp peer <*>"
set policy-options prefix-list snmp-sources-v4 apply-path "snmp client-list <*> <*>"
set policy-options prefix-list local-management-v4 apply-path "interfaces fxp0 unit <*> family inet address <*>"
set policy-options prefix-list uac-servers-v4 apply-path "services unified-access-control infranet-controller <*> address <*>"
set policy-options prefix-list radius-servers-v4 apply-path "system radius-server <*>"
set policy-options prefix-list name-servers-v4 apply-path "system name-server <*>"
set policy-options prefix-list management-sources-v4 10.160.0.0
set policy-options prefix-list management-sources-v4 10.162.0.0
set policy-options prefix-list management-sources-v4 10.196.88.22
set policy-options prefix-list management-sources-v4 10.196.192.0
set policy-options prefix-list management-sources-v4 10.222.0.0
set policy-options prefix-list management-sources-v4 10.228.0.0
set policy-options prefix-list management-sources-v4 10.234.0.0
set policy-options prefix-list ip-scanners-v4 10.196.0.184
set policy-options prefix-list ip-scanners-v4 10.196.193.44
set policy-options prefix-list ip-scanners-v4 10.196.193.49
set policy-options prefix-list ip-scanners-v4 10.196.193.50
set policy-options prefix-list ip-scanners-v4 10.201.4.0
set policy-options prefix-list ip-scanners-v4 10.222.4.10
set policy-options prefix-list ip-scanners-v4 10.222.94.152
set policy-options prefix-list ip-scanners-v4 10.222.240.249
set policy-options prefix-list ip-scanners-v4 10.223.128.4
set policy-options prefix-list ip-scanners-v4 66.54.64.143