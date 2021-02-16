# fieldLAN
A project to rapidly deploy (pretty) scalable networks in very rural areas

## Introduction
Since I am frequently doing Networking and Internet for summer camps, it has become really useful to have a setup in an Rack that can be quickly deployed in such environments.

## Hardware (in one rack)
The routing hardware consists of an old but somewhat trustworthy Juniper SRX220 (ca. 50-100 Euro on eBay). They can be configured in failover configurations so there would be two nodes that take over traffic if one of them goes down.
The switching hardware consists of one Cisco 24-Port Gigabit Managed Switch.
The Wifi Hardware is powered by 4 of Ubiquitis UniFi AP-AC-M Accesspoints (ca. 75 Euro on eBay) and 4 external POE-Injectors mounted in the Rack itself.
Also an OrangePi Zero that runs the UniFi controller software. 
The Rack can be either powered via 12V Solar power and an Inverter or via the build in UPS (An old APC UPS) via an outlet.
The Rack itself is a modified [Thomann Rack Case 4U](https://www.thomann.de/intl/thomann_rack_case_4u.htm) that was fitted with water and weatherproof cable holes and was weather proofed (Somewhat! If it rains constantly, it may get kinda wet.).
The Electronics inside get a bit warm but when equipped with new thermal paste and a small coolant exaust, heat is not a real problem.

## Uplinks
The whole System is very flexible when it comes to uplinks. I myself have 3 LTE-Uplinks (Vodafone GigaCube in a Waterproof Housing with external antennas, O2 WifiSpot with external antennas and a no-name chinese Router). Usually when used in conjunction with high gain antennas and a tree, they deliver around 50/50 even in the deepest valleys of the black forest where no phones have any reception. When bundled and load balanced, I get around 150-300 mbit over that connection.
For locations with an available DSL/Phone line, there are short-term DSL plans available at most Carriers. For that I keep an old Fritz!Box around to get another 10-200 mbit down and some additional 2-50 mbit up.
Since the network and internet is often only for organizers of the camps, the bandwith is more than enough. If requested I also bring a 10TB NAS with me for local filesharing.

## Telephony
If telephony is requested, I have a cheap german SIP-Trunk and a freepbx installation that can be added to the rack in a matter of minutes. People on the camp can then either a SIP-Client on their phones or a SIP(LAN) to Analog client for analog telephones. But the SIP thing covers most of the applications. 

## Networking Setup
### Internal LAN
10.0.1.0/24
- DHCP-Range: 10.0.1.100 - 10.0.1.250
- VLAN 10

### Guest LAN
10.0.2.0/24
- DHCP-Range: 10.0.2.50 - 10.0.2.250
- Captive portal at 10.0.2.1
- Link limited to 1mbit/1mbit
- VLAN 20

### Management LAN
10.0.0.0/24
- DHCP-Range: 10.0.0.120 - 10.0.0.250
- APs
  - AP1: 10.0.0.10
  - AP2: 10.0.0.11
  - AP3: 10.0.0.12
  - AP4: 10.0.0.13
- Full access to all VLANS
- VLAN 10, 20
- Juniper: 10.0.0.1
