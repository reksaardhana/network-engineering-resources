# Skrip Python untuk Jaringan

Berikut adalah beberapa skrip Python yang berguna untuk insinyur jaringan.

## Contoh Skrip
### 1. Ping Sweep
```python
import os

def ping_sweep(ip_range):
    for i in range(1, 255):
        ip = f"{ip_range}.{i}"
        response = os.system(f"ping -c 1 {ip}")
        if response == 0:
            print(f"{ip} is up")
        else:
            print(f"{ip} is down")

ping_sweep("192.168.1")
```

### 2. Automasi Konfigurasi Cisco
```python
from netmiko import ConnectHandler
device = {
    'device_type': 'cisco_ios',
    'host': '192.168.1.1',
    'username': 'admin',
    'password': 'password',
}

connection = ConnectHandler(**device)
output = connection.send_command('show ip int brief')
print(output)
connection.disconnect()
```
