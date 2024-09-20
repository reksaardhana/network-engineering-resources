```markdown
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
