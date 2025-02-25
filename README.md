# Before running the script, ensure you have the following:

Linux Environment: This script is designed to run on Linux (e.g., Ubuntu, Kali Linux).

Python 3: The script requires Python 3 to run.

Scapy Library: Install Scapy, a Python library used for packet manipulation.

Wireless Adapter: You need a wireless adapter that supports monitor mode. Most Wi-Fi adapters with the iw or iwconfig tools can be used.

Root Privileges: The script must be run as root to enable monitor mode and send deauthentication packets

#  Running the Script

 To run the script, use the following command structure:

sudo python3 wifi_deauth.py -i <interface> [options]

# Required Arguments

-i or --iface: Specify the wireless interface (e.g., wlan0).

#   Optional Arguments:

--skip-monitormode: Skip the automatic setup of monitor mode (use this if your interface is already in monitor mode).

-k or --kill: Kill the NetworkManager service (recommended to avoid interference).

-s or --ssid: Specify a target SSID (case-insensitive).

-b or --bssid: Specify a target BSSID (MAC address of the access point).

--clients: Specify target client MAC addresses (comma-separated, e.g., 00:1A:2B:3C:4D:5E,00:1A:2B:3C:4D:5F).

-c or --channels: Specify custom channels to scan/deauth (comma-separated, e.g., 1,6,11).

-a or --autostart: Automatically start the deauthentication attack if only one access point is found.

-d or --debug: Enable debug mode for more detailed output.

--deauth-all-channels: Enable deauthentication on all channels (useful for multi-channel attacks).


# Example Commands

 sudo python3 wifi_deauth.py -i wlan0 ( Scan for access points and select a target manually )

sudo python3 wifi_deauth.py -i wlan0 -s karmawifi (Attack a specific SSID (e.g., karmaWiFi)

sudo python3 wifi_deauth.py -i wlan0 -b 00:1A:2B:3C:4D:5E ( Attack a specific access point by its BSSID (MAC address)

sudo python3 wifi_deauth.py -i wlan0 --clients 00:1A:2B:3C:4D:5E,00:1A:2B:3C:4D:5F ( Attack specific clients connected to the access point )

sudo python3 wifi_deauth.py -i wlan0 --deauth-all-channels (Perform deauthentication on all channels)

sudo python3 wifi_deauth.py -i wlan0 -d ( Enable debug mode for detailed output )

# NOTE
Only use this script on networks you own or have explicit permission to test. Unauthorized use is illegal and unethical.
