# unifi-usg-kpn
Unifi USG Configuration for use with KPN FTTH


Simple configuration to implement Ubiquiti Unifi USG router with Dutch FTTU provider KPN Glasvezel.

Hardware: Ubiquiti Unifi USG-3 Firmware 4.4.18.5052168
Software: Unifi version 5.6.30

To easy setup: Download and edit config.gateway.json and search for @kpn. Fill in your router mac-address and save json file.
My router ip-address is 192.168.2.254 , please change all you can find in this json to the one you want.

I've connect to Experiabox v10 WAN port to USG LAN2, as workaround to enable telephony, because KPN doesn't provide VOIP settings.
Please do NOT enable "Use VOIP as WAN2" option in Unifi.


Upload config.gateway.json to your Unifi setup to /usr/lib/unifi/data/sites/default

Go to: USG -> Device Management and click Force provision



Dynamic IPTV route updates:
Upload update_iptv_route.sh to your USG to /config/scripts/post-config.d/
Execute: chmod +x /config/scripts/post-config.d/update_iptv_route.sh


Configuration based by:
https://github.com/basmeerman/unifi-usg-kpn
https://www.byluke.nl/tutorial/ubiquiti-usg-werkend-krijgen-kpn-glasvezel/


Known errors:
- IPv6 ping is fluctuating.
- When this LAN2 port stay in a disconnected state, please add a dummy network to this port. This is a Unifi Bug.
- IPSec VPN not working. I've not on research this one. PPTP is working.
