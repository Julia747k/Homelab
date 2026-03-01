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

#### Step 1: Edit logind configuration

```bash
sudo vim /etc/systemd/logind.conf
```
#### Step 2: Modify lid behavior

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

#### Step 3: Restart the service

```bash
sudo systemctl restart systemd-logind
```

Now the laptop stays running with the lid closed 🥳

## 🌐 Remote Access with Tailscale
I set up Tailscale so I can access my homelab from my MacBook anywhere.


Honestly the setup was super easy.
#### Step 1: Install Tailscale

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

#### Step 2: Bring Talescale up

```bash
tailscale up
```

After running it: 

It generates a login link
1. Go to the link and create/log into your account. 
2. [Download](https://tailscale.com/download/linux) Tailscale on you machine based on the OS, and connect it to the same tailnet.

Now i can access my Proxmox server from anywhere ☺️

## 📸 Homelab (So Far)

I'll be posting pictures of the setup here.

⚠️ Warning: It looks a bit funny right now 😝

<img width="1598" height="962" alt="image" src="https://github.com/user-attachments/assets/b740f339-4ae7-4098-b8d2-f29a67eff3ae" />


## 🗺️ Roadmap
Things I plan to explore next:

//TODO

## 📬 Follow the Journey
This repo will evolve as the lab grows.
Suggestions and tips are always welcome!
