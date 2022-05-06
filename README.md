# boatreporter
Reports your boat's position to MarineTraffic.com by reading NMEA2000 data (using canboat) or NMEA0183 (using kplex tcp server) and sending report via e-mail.

Example command-lines:

reporter0183 333444555 report@marinetraffic.com

reporter2000 333444555 report@marinetraffic.com

Please, do NOT make reports with other MMSI-numbers than your own!

# gpiozero

Utility script that reads a Raspberry PI GPIO pin and exits with code 0 or 1 depending on the state. Can be used to enable or disable sending a periodic report.

Example cronjob that checks GPIO pin #3, checks internet availability, and then sends report:

gpiozero 3 && ping -c 1 8.8.8.8 > /dev/null && reporter0183 333444555 report@marinetraffic.com
