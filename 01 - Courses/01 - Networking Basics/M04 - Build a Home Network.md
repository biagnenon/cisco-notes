---
course: Networking Basics
module: "04"
module-name: Build a Home Network
type: Topic
status: in-progress
difficulty: 1
tags:
  - cisco
  - netacad
  - topic
  - networking-basics
  - wlan
  - home-network
created: 2026-11-23
last-reviewed: 2026-11-24
---
# Build a Home Network

> [!summary] TL;DR
> A home network is built around a wireless router that bridges a **LAN** (Ethernet + Wi-Fi clients) to a **WAN** (the ISP). Configure an integrated wireless router and wireless client to connect securely to the internet using **DHCP** for addressing and **WPA2 Personal** for Wi-Fi security.

## Learning Objectives

- Learn the components required to build a home network
- Understand wired and wireless technologies
- Understand Wi-Fi
- Configure wireless device for secure communications

## Key Concepts

- WLAN
- Router
- Ethernet port
- Internet port
- 2.4GHz / 5GHz
- 802.11 protocol
- SSID
- Frame
- DHCP
- WPA2 Personal
- Cable modem
- Coaxial cable / splitter (for cable ISP service)

## Notes

### Home Network Basics

Most home networks consist of at least two separate networks. The **service provider** usually provides the **public network (WAN)**. The homeowner builds a **private network (LAN)** on the inside.

A **router** is a networking device that connects different networks and forwards data between them based on destination IP addresses. In a home, it links the LAN to a WAN like the internet.

Small business and home routers typically have two primary types of ports:

- ***Ethernet ports*** — connect to the internal **switch** portion of the router. All devices connected to the switch ports are on the **same local network**.
- ***Internet port*** — used to connect the router to **another network** (a different network than the Ethernet ports). It is typically used to connect to a **cable or DSL modem** for internet access.

Many home routers include a radio antenna and a built-in **wireless access point (WAP)**. By default, wireless devices are on the **same local network** as the devices plugged into the Ethernet ports.

> [!tip] Cable-ISP topology (as seen in the lab)
> Coax from the wall → **Cable Splitter** → splits to (1) **Cable Modem** (internet data) and (2) **TV** (video).
> The modem's Ethernet port then connects to the router's **Internet port** via a **copper straight-through** cable.
> **Do not** connect coax directly to a wireless router.

### Network Technologies in the Home

The wireless technologies most frequently used in home networks are the unlicensed **2.4 GHz** and **5 GHz** frequency ranges.

- **Bluetooth** also uses the 2.4 GHz band.
- **802.11 (Wi-Fi)** devices use the same bands but transmit at **much higher power**, giving them **greater range** and **improved throughput**.

**2.4 GHz vs 5 GHz trade-offs:**

| | 2.4 GHz | 5 GHz |
|---|---|---|
| Range | Longer | Shorter |
| Wall penetration | Better | Worse |
| Interference | More (microwaves, Bluetooth, neighbors) | Less |
| Channels | Fewer | More |
| Max throughput | Lower | Higher |

The most common implemented **wired** protocol is **Ethernet**. Ethernet uses a suite of protocols that allow network devices to communicate over a wired LAN connection.

### Wireless Standards

A number of standards have been developed to ensure that wireless devices can communicate. They specify the RF spectrum used, data rates, how information is transmitted, and more.

- **IEEE** (Institute of Electrical and Electronics Engineers) — creates the wireless technical standards, including **802.11**.
- **Wi-Fi Alliance** — tests wireless LAN devices from different manufacturers for compliance (the "Wi-Fi Certified" logo).

**802.11 standards overview:**

| Standard | Band(s) | Nominal max rate |
|---|---|---|
| 802.11b | 2.4 GHz | 11 Mbps |
| 802.11g | 2.4 GHz | 54 Mbps |
| 802.11n (Wi-Fi 4) | 2.4 / 5 GHz | 600 Mbps |
| 802.11ac (Wi-Fi 5) | 5 GHz | ~1+ Gbps |
| 802.11ax (Wi-Fi 6/6E) | 2.4 / 5 / 6 GHz | ~9.6 Gbps |

Wireless routers using the 802.11 standard have multiple settings that must be configured:

- **Network Mode** — determines the type of technology that must be supported (802.11b, 802.11g, 802.11n, or mixed mode).
- **Network Name (SSID)** — used to identify the WLAN. All devices that wish to participate in the WLAN must have the **same SSID**.
- **Standard Channel** — specifies the channel over which communication will occur. Set to **Auto** by default to allow the AP to choose the optimum channel.
- **SSID Broadcast** — determines if the SSID will be broadcast to all devices within range. **Enabled by default**.

**Mixed mode** network environments can include devices that use any of the existing Wi-Fi standards. The 802.11 protocol can provide improved throughput based on the wireless network environment — **if all devices connect with the same 802.11 standard, maximum speed can be obtained for that standard.**

The **SSID (Service Set Identifier)** is a **case-sensitive**, alphanumeric string of up to **32 characters**. It is sent **in the header of all frames** transmitted over the WLAN — meaning even if SSID Broadcast is disabled, the SSID is still visible in the frame headers of associated traffic, so hiding it is **not a real security control**.

**Wireless security progression (weakest → strongest):**

- **WEP** — broken, never use
- **WPA** — deprecated
- **WPA2 Personal** — uses a **Pre-Shared Key (PSK)** passphrase; strongest offered by most home routers in this module
- **WPA3** — newest; uses SAE (Simultaneous Authentication of Equals); best if supported

### Set up a Home Router

Many wireless routers designed for home use have an **automatic setup utility** that can be used to configure the basic settings.

Most network routers are set up so that the computer **receives an IP address automatically** from a **local DHCP server** running on the wireless router. If the device does not have an IP address, check the router documentation and configure the device with a **unique IP address, subnet mask, default gateway, and DNS information**.

**DHCP** (Dynamic Host Configuration Protocol) automatically provides:
- IP address (typically `192.168.x.x` on a home LAN)
- Subnet mask
- Default gateway (= the router's LAN IP)
- DNS server(s)

**Typical configuration workflow (from the lab):**

1. Connect wired PC → set **DHCP** → note default gateway → open web browser → browse to the gateway IP.
2. Log in with **default credentials** (`admin`/`admin`).
3. Setup → Network Setup → **Maximum Number of Users** = 10 → **Save Settings**.
4. Administration → set new admin password → **Save Settings** → re-login.
5. Wireless → **Enable** the 2.4 GHz radio; set **SSID** (e.g. `MyHome`) → **Save Settings**.
6. Wireless Security → 2.4 GHz → **WPA2 Personal** → set passphrase → **Save Settings**.
7. On wireless clients: connect to SSID, enter passphrase (PSK).
8. Verify clients received `192.x.x.x` and can load an external site.

> [!warning] Security
> Default passwords (like `admin`/`admin`) are **widely known to threat actors** and must be changed **immediately** on real devices. On any router, keep firmware updated and disable remote management.

## Real-World Connection

- **At home / small office:** The same workflow applies to a Linksys, Netgear, TP-Link, or ASUS home router — log into `192.168.0.1` / `192.168.1.1`, change admin credentials, rename the SSID, enable WPA2/WPA3, and let DHCP serve clients.
- **In CCNA:** This module sets up the "router as default gateway + DHCP server + WAP" mental model that reappears as **inter-VLAN routing**, **DHCP relay (`ip helper-address`)**, **WLC configuration**, and **WPA2-Enterprise (802.1X)**.
- **ISP side:** The "cable modem + splitter" topology is the same reason a cable subscriber can have TV + internet simultaneously — the splitter keeps the two services on the same physical medium.

## Gotchas / Exam Traps

- A router's **Ethernet** and **Internet** ports each connect devices to **different networks** — Ethernet = LAN switch side, Internet = WAN side.
- **Coax never plugs directly into a wireless router.** It goes splitter → **modem** → (Ethernet) router **Internet** port.
- **Default gateway = router's LAN IP** — that's the address clients use to leave the LAN, and the address you browse to in order to reach the router's GUI.
- **SSID is case-sensitive** and up to **32 characters**. `MyHome` ≠ `myhome`.
- **SSID is in every frame header** — hiding the SSID is **not** encryption. WPA2/WPA3 is what secures the link.
- **WPA2 Personal = PSK (pre-shared key/passphrase).** WPA2 Enterprise uses 802.1X/RADIUS — different animal; home routers usually only do Personal.
- **Mixed mode** = slower for everyone. Pure-standard mode = faster.
- **Change default admin credentials immediately** — `admin`/`admin` is a known-vulnerable default.
- **"Maximum Number of Users"** limits how many DHCP leases the router will issue — useful for small home networks; too low and legitimate guests get no address.
- After **Save Settings**, you may **lose your GUI session** — just re-browse to the gateway IP and log in again.
- DHCP delay in Packet Tracer: use **Fast Forward Time** to speed up lease negotiation.

## Related Modules

- Previous: [[M03 - ...]]
- Next: [[M05 - ...]]
- Related: [[L01 - Packet Tracer - Configure a Wireless Router and Clients]] (this module's lab)

## Self-Test Questions

1. Which two ports on a home router connect to different networks, and what does each connect to?
2. What is the difference between **WPA2 Personal** and **WPA2 Enterprise**?
3. If a client connects to Wi-Fi but gets a `169.254.x.x` address, what most likely failed, and what is that address type called?
4. Why is **disabling SSID broadcast not considered a security measure**?
5. What are the trade-offs between **2.4 GHz** and **5 GHz** for a home WLAN?
6. In a cable-ISP home setup, what device sits between the **coaxial splitter** and the **wireless router**, and what type of cable connects it to the router?
7. Which IEEE working group owns the **802.11** standard, and which organization certifies interoperability between vendors?

## Resources

- [x] NetAcad module content
- [x] Checkpoint exam
- [x] Lab: [[L01 - Packet Tracer - Configure a Wireless Router and Clients]]
