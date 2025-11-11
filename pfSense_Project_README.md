
# 🔐 pfSense Home Firewall Project

## 🧾 Overview
This project documents the setup of a home firewall using **pfSense** on a Dell OptiPlex 3070 Small Form Factor desktop. The goal is to create a secure, segmented home network with VLANs, firewall rules, and monitoring capabilities.

## 🖥️ Hardware
- **Firewall Host**: Dell OptiPlex 3070 SFF
- **NIC Upgrade**: Intel i210-T1 (Gigabit Ethernet, single port)
- **Router**: NETGEAR XR1000-100APS
- **Switch**: TP-Link TL-SG108E Smart Managed Switch
- **ISP**: NBN (Australia)

## 🌐 Network Topology
```
NBN Box → pfSense (WAN)
pfSense (LAN) → TP-Link TL-SG108E → VLAN Devices
pfSense (LAN) → NETGEAR XR1000 (Access Point Mode)
```

## ⚙️ Setup Steps
1. Install pfSense on the OptiPlex 3070.
2. Install Intel i210-T1 NIC to provide a second Ethernet port.
3. Assign interfaces during pfSense setup:
   - `em0` → WAN (Intel NIC)
   - `em1` → LAN (Onboard NIC)
4. Connect WAN to NBN box and LAN to TP-Link switch.
5. Set XR1000 to Access Point mode to avoid double NAT.

## 🧩 VLAN Configuration
- Create VLANs in pfSense:
  - VLAN 10 → IoT Devices
  - VLAN 20 → Gaming
  - VLAN 30 → Work
- Assign VLANs to LAN interface.
- Configure TP-Link switch:
  - Tag trunk port (pfSense LAN)
  - Assign untagged VLANs to access ports
- Connect devices to appropriate VLAN ports.

## 📈 Features Enabled
- 802.1Q VLAN tagging
- Firewall rules per VLAN
- QoS and IGMP Snooping
- Port Mirroring for diagnostics
- VPN setup (optional)

## 📸 Screenshots & Diagrams
![[Pasted image 20251105124830.png]]

## 🔗 Resources
- [Intel i210-T1 NIC on Scorptec](https://www.scorptec.com.au/product/networking/adapters/103015-i210t1)
- [TP-Link TL-SG108E Switch](https://www.tp-link.com/au/business-networking/soho-switch-easy-smart/tl-sg108e/)
- [pfSense Setup Guide](https://www.youtube.com/watch?v=USVkw3ZY7fo)
- [Zero to Hero pfSense Configuration](https://www.youtube.com/watch?v=he3ENpMLMsc)
- [Bonus VPN Setup](https://www.youtube.com/watch?v=iHw62D0t-2M)

---

📌 *Maintained by Sourav Biswas — IT Helpdesk Support | Networking & Cloud Enthusiast*
