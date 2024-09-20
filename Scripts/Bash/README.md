
# Skrip Bash untuk Jaringan

Berikut adalah beberapa skrip Bash yang berguna untuk insinyur jaringan.

## Contoh Skrip
### 1. Backup Konfigurasi Cisco
  ```bash
  #!/bin/bash
  HOST="192.168.1.1"
  USER="admin"
  PASS="password"

  sshpass -p $PASS ssh $USER@$HOST "show running-config" > backup_config.txt
### 2. Monitor Jaringan
```bash
#!/bin/bash
while true; do
    ping -c 1 192.168.1.1 > /dev/null
    if [ $? -eq 0 ]; then
        echo "$(date): Host is up" >> network_log.txt
    else
        echo "$(date): Host is down" >> network_log.txt
    fi
    sleep 60
done
