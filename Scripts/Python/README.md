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

