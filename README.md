# Redis Rogue Server (Tunneling Version)

Modified to support for **Red Team operators, CVE research, exploit labs, and controlled penetration testing**:

[+] Pinggy / Cloudflare Tunnel / Ngrok reverse tunnels  
[+] Custom **local bind port** (`--bind`)  


> **Disclaimer**  
> This tool must be used for **authorized security testing only**.  
> You are fully responsible for how you use this code.

---

## Features

- Rogue Redis replication server (PSYNC/SYNC handler)
- Supports modules injection via `<exp.so>`  [RedisModules-ExecuteCommand (fixed module.c error)](https://github.com/netw0rk7/RedisModules-ExecuteCommand) 
- Works with reverse tunnels (Pinggy, Cloudflare, Ngrok)
- Configurable **local bind port** (`--bind`)
- Interactive shell (`system.exec`)
- Automatic RCE chain:
  - SLAVEOF → send malicious payload → load module → execute commands
- Automatic cleanup after exploitation

---

## Requirements

- Python 3.8+
- Redis target with:
  - `slaveof` enabled  
  - `CONFIG SET` enabled  
- Forwarding tool (optional):
  - Pinggy  
  - Cloudflare Tunnel  
  - Ngrok  
  - SSH reverse tunnel  

---

## Installation

```bash
git clone https://github.com/netw0rk7/redis-rogue-server
cd redis-rogue-server
python3 redis-rogue.server.py --help
```



<img width="829" height="700" alt="image" src="https://github.com/user-attachments/assets/71698f11-691e-4824-b82b-2df495d994b4" />
