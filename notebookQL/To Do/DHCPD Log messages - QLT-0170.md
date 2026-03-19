ACX Routers are spammed with DHCPD entries in the messages log. We do not use DHCP so this is either internal communication or something is broken. Either way it's useless noise. See if these can be suppressed somehow. Raise vendor ticket if needed. Note these are still present as of version 25.4R1 so an upgrade doesn't seem to hide them

- [[#Updates]]

```
Mar 17 08:58:22  HG3-DLY-EDGE-1-re0 dhcpd[6657]: Server starting service.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Internet Systems Consortium DHCP Server 4.4.2
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Copyright 2004-2021 Internet Systems Consortium.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: All rights reserved.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: For info, please visit https://www.isc.org/software/dhcp/
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Wrote 0 class decls to leases file.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Wrote 0 deleted host decls to leases file.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Wrote 0 new dynamic host decls to leases file.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Wrote 0 leases to leases file.
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Multiple interfaces match the same subnet: vmb0 vib
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Multiple interfaces match the same shared network: vmb0 vib
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Multiple interfaces match the same subnet: vmb0 vib
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Multiple interfaces match the same shared network: vmb0 vib
Mar 17 09:13:23  HG3-DLY-EDGE-1-re0 dhcpd[5230]: Server starting service.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Internet Systems Consortium DHCP Server 4.4.2
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Copyright 2004-2021 Internet Systems Consortium.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: All rights reserved.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: For info, please visit https://www.isc.org/software/dhcp/
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Wrote 0 class decls to leases file.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Wrote 0 deleted host decls to leases file.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Wrote 0 new dynamic host decls to leases file.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Wrote 0 leases to leases file.
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Multiple interfaces match the same subnet: vmb0 vib
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Multiple interfaces match the same shared network: vmb0 vib
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Multiple interfaces match the same subnet: vmb0 vib
Mar 17 09:28:24  HG3-DLY-EDGE-1-re0 dhcpd[3592]: Multiple interfaces match the same shared network: vmb0 vib
```


# Updates:
Xantaro ticket opened: XTAC-6147