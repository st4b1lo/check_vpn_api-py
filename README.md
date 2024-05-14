I created these two scripts as a starting point for those who need to extract data from multiple Fortigate firewall connected to Fortimanager devices. 
The scripts in question act in a different way:


"check_vpn_api.py" one uses as a method to get the API requests which are sent directly from the fortimanager to the fortigates, in this way you have a real-time overview of what is present in the device, this is useful in case the Policy Package on the fortimanager is not aligned with the configuration present on the fortigate firewalls but also more complex in indexing the data as the responses are provided in json


"check_https-exposed_ssh.py" uses as a data acquisition method exclusively via ssh connection to the fortimanager, by executing the command f"execute fmpolicy print-device-object {name} {row[1]} 3 8 Internet" and dynamically taking the previously extracted devices you can speed up the extraction of everything present on the fortimanager. In this case the requests are not proxed.
