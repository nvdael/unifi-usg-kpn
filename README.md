# unifi-usg-kpn
Unifi USG Configuration for use with KPN FTTH


Simple configuration to implement Ubiquiti Unifi USG router with Dutch FTTU provider KPN Glasvezel. </br>

Hardware: Ubiquiti Unifi USG-3 Firmware 4.4.22.5086045 </br>
Software: Unifi CloudKey version 5.8.24-11016 / Firmware UCK.mtk7623.v0.11.4.a7e4cad.180629.1434 </br>

To easy setup: Download and edit config.gateway.json and search for @kpn. Fill in your router mac-address and save json file. </br>
My router ip-address is 192.168.2.254 , please change all you can find in this json to the one you want. </br>

I've connect to Experiabox v10 WAN port to USG LAN2, as workaround to enable telephony, because KPN doesn't provide VOIP settings. </br>
Please do NOT enable "Use VOIP as WAN2" option in Unifi. </br>


Upload config.gateway.json to your Unifi setup to /usr/lib/unifi/data/sites/default </br>

Go to: USG -> Device Management and click Force provision </br>



Dynamic IPTV route updates: </br>
Upload update_iptv_route.sh to your USG to /config/scripts/post-config.d/ </br>
Execute: chmod +x /config/scripts/post-config.d/update_iptv_route.sh </br>


Configuration based by: </br>
https://github.com/basmeerman/unifi-usg-kpn </br>
https://www.byluke.nl/tutorial/ubiquiti-usg-werkend-krijgen-kpn-glasvezel/ </br>


Known errors: </br>
- IPv6 ping is fluctuating.
- When this LAN2 port stay in a disconnected state, please add a dummy network to this port. This is a Unifi Bug.
- IPSec VPN not working. I've not on research this one. PPTP is working.
