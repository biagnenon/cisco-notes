---
course: Networking Basics
type: Lab
module: "[[M04 - Build a Home Network]]"
status: in-progress
tool: Packet Tracer
tags:
  - cisco
  - netacad
  - lab
  - networking-basics
created: 2026-11-24
---
# Packet Tracer - Configure a Wireless Router and Clients

> [!info] Objective
> Connect the Devices
> Configure the Wireless Router
> Configure IP Addressing and Test Connectivity

## Topology

![[Topology - Configure a Wireless Router and Clients.jpg]]

| From           | Port          | To                   | Port                         | Cable                   |
|----------------|---------------|----------------------|------------------------------|-------------------------|
| Cable Splitter | Coaxial1      | Cable Modem          | Port 0                       | Coaxial                 |
| Cable Splitter | Coaxial2      | TV                   | Port 0                       | Coaxial                 |
| Cable Modem    | Port 1        | Home Wireless Router | Internet                     | Copper Straight-Through |
| Office PC      | FastEthernet0 | Home Wireless Router | GigabitEthernet 1            | Copper Straight-Through |
| Bedroom PC     | FastEthernet0 | Home Wireless Router | GigabitEthernet 2            | Copper Straight-Through |
| Laptop         | Wireless NIC  | Home Wireless Router | 2.4 GHz Radio (SSID: MyHome) | Wireless                |

## Tasks

- [x] Task 1: Connect the Devices
- [x] Task 2: Configure the Wireless Router
- [x] Task 3: Configure IP Addressing and Test Connectivity

## Key Configurations

### Cable Splitter

- Coaxial1 → Cable Modem Port 0
- Coaxial2 → TV Port 0
- Separates internet data service from video service

### Cable Modem

- Coaxial from Cable Splitter → Port 0
- Port 1 → Home Wireless Router **Internet** port (Copper Straight-Through)

### TV

- Coaxial from Cable Splitter (Coaxial2) → Port 0
- **Status: ON** (image appears when cabling is correct)

### Home Wireless Router

- **Internet port** ← Cable Modem Port 1 (Copper Straight-Through, _not_ coax)
- **GigabitEthernet 1** ← Office PC FastEthernet0
- **GigabitEthernet 2** ← Bedroom PC FastEthernet0

**GUI configuration (accessed from Office PC web browser via default gateway IP starting with `192.168.x.x`):**

| Location in GUI                        | Setting                 | Value                            |
|----------------------------------------|-------------------------|----------------------------------|
| Login                                  | User Name / Password    | admin / admin                    |
| Setup → Network Setup                  | Maximum Number of Users | 10                               |
| Administration                         | New password            | MyPassword1!                     |
| Wireless → 2.4 GHz                     | Radio                   | Enable                           |
| Wireless → 2.4 GHz                     | Network Name (SSID)     | Default → MyHome                 |
| Wireless → Wireless Security → 2.4 GHz | Security Mode           | WPA2 Personal                    |
| Wireless → Wireless Security → 2.4 GHz | Passphrase              | MyPassPhrase1!                   |

Every page must be saved with **Save Settings** before moving on.

### Office PC

- IP Configuration: **DHCP** (obtained `192.x.x.x` address)
- Used to access the router GUI and to verify internet (load `skillsforall.srv`)
- Connect to router **GigabitEthernet 1**
    

### Bedroom PC

- IP Configuration: **DHCP** (obtained `192.x.x.x` address)
- Verified internet via `skillsforall.srv`
- Connect to router **GigabitEthernet 2**

### Laptop

- Desktop → **PC Wireless** → Connect tab
- Selected SSID: `MyHome`
- Pre-shared Key: `MyPassPhrase1!`
- Link Information confirms **"You have successfully connected to the access point"**
- More Information → DHCP IP starting with `192`
- Verified internet via `skillsforall.srv`

## Expected Output / Success Criteria

- **Office PC**, **Bedroom PC**, and **Laptop** all receive `192.x.x.x` DHCP addresses
- All three clients successfully load **`skillsforall.srv`** in the Web Browser → confirms full wired + wireless internet connectivity
- TV displays a program image when powered **ON** (confirms coax/splitter cabling is correct)
- Laptop shows **"You have successfully connected to the access point"** in PC Wireless → Link Information

## What Broke / Lessons Learned

- Nothing broke.
- Learned how to connect devices (coax vs. copper straight-through cabling).
- Learned how to configure a home wireless router via its GUI.
- Learned how to configure IP addressing (DHCP) and test connectivity.
- DHCP automatically assigns addresses and network settings — no manual IP entry needed for clients.
- **Default credentials (`admin`/`admin`) must be changed immediately** — widely known to threat actors.
- Limiting **Maximum Number of Users** on DHCP is a simple way to cap how many clients the router will serve.
- **WPA2 Personal** is the strongest wireless security option on this router; a passphrase is required for any device joining the network.
- The router's **Internet port** connects to the modem — coax never plugs directly into a home router.

## Related Topic Notes

- [[M04 - Build a Home Network]]

---


