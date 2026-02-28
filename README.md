# 🤓 Homelab Journey

Welcome to my homelab journey!  
This repo documents my experiments, mistakes, wins, and lessons learned while building 
a small but growing home lab environment.

---

## 🥀 Current Setup

My homelab currently runs on an **old laptop repurposed as a server** running Proxmox.

### 🖥️ Hardware Specs

- **CPU:** Intel Core i3-6100U @ 2.30GHz  
- **RAM:** 4GB  
- **Platform:** Lenovo L4600
- **Hypervisor:** Proxmox VE  

---


## Preventing Sleep When Lid Is Closed

Since I'm using a laptop as a server, I needed it to **stay on with the lid closed**.

### Step 1: Edit logind configuration

```bash
sudo vim /etc/systemd/logind.conf
```
### Step 2: Modify lid behavior

Find these lines:

```bash
#HandleLidSwitch=suspend
#HandleLidSwitchExternalPower=suspend
#HandleLidSwitchDocked=ignore
```

Change them to: 

```bash
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
```

### Step 3: Restart the service

```bash
sudo systemctl restart systemd-logind
```

Now the laptop stays running with the lid closed 🥳


## 📸 Homelab (So Far)

I'll be posting pictures of the setup here.

⚠️ Warning: It looks a bit funny right now 😝

## 🗺️ Roadmap
Things I plan to explore next:

//TODO

## 📬 Follow the Journey
This repo will evolve as the lab grows.
Suggestions and tips are always welcome!
