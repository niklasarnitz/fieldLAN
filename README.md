# fieldLAN
A project to rapidly deploy (pretty) scalable networks in very rural areas

## Introduction
Since I am frequently doing Networking and Internet for summer camps, it has become really useful to have a setup in an Rack that can be quickly deployed in such environments.

## Hardware (in one rack)
The routing hardware consists of an old but somewhat trustworthy Juniper SRX220. They can be configured in failover configurations so there would be two nodes that take over traffic if one of them goes down.
The switching hardware consists of one Cisco 24-Port Gigabit Managed Switch.
The Wifi Hardware is powered by 4 of Ubiquitys Unifi AC-AP-HD Accesspoints and 4 external POE-Injectors mounted in the Rack itself.
Also an OrangePi Zero that runs the UniFi controller software. 
The Rack can be either powered via 12V Solar power and an Inverter or via the build in UPS (An old APC UPS) via an outlet.
The Rack itself is a modified [Thomann Rack Case 4U](https://www.thomann.de/intl/thomann_rack_case_4u.htm) that was fitted with water and weatherproof cable holes and was weather proofed (Somewhat! If it rains constantly, it may get kinda wet.).
The Electronics inside get a bit warm but when equipped with new thermal paste and a small coolant exaust, heat is not a real problem.
