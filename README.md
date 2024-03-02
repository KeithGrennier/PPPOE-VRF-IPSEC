# PPPOE-VRF-IPSEC
Cisco CML, PPPoE, IPSec with VRF at Spoke Site
# HQ
HQ: 100.100.100.1
# ISP
ISP/HQ: 100.100.100.2

ISP/Spoke: 42.42.42.42
# SPOKE
PPPoE: 201.201.201-210
Kinda annoying

Spoke: Assigned by pppoe
- 201.201.201.201
- 201.201.201.202
```
Internal IP
- 192.168.20.1
```
## PC
- 192.168.20.2


# Learning Note
After conducting this setup, I found out after many hours that if this field is not negotiated and instead ip x.x.x.x y.y.y.y, the tunnel cause some issues. Namely you'll be unable to ssh to the device. The tunnel will fail after a while. Very confusing and frustrating.
```
interface Dialer1
 mtu 1492
 ip vrf forwarding INET
 ip address negotiated
```
