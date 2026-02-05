
# Cisco Project — DMZ Architecture + Zone-Based Firewall (ZBF) + NAT (Packet Tracer)

This repo is a **real enterprise-style DMZ build** using a Cisco router as the security perimeter.
It demonstrates how to publish **public services** (Web + DNS) safely in a **DMZ**, while protecting the inside LAN with a **Zone-Based Firewall** and controlled NAT.

---

## ✅ What this project includes

- Classic **3-zone design**: INSIDE / DMZ / OUTSIDE
- **Zone-Based Firewall (ZBF)**:
  - OUTSIDE → DMZ: allow only public services (HTTP/HTTPS/DNS)
  - OUTSIDE → INSIDE: **blocked**
  - INSIDE → OUTSIDE: allowed + stateful return traffic
  - INSIDE → DMZ: allowed (admin + app access)
  - DMZ → INSIDE: blocked (DMZ should not initiate to LAN)
- **Static NAT** (publish DMZ servers)
- **PAT** (LAN clients to internet)
- Clear addressing plan + verification steps

---

## Topology overview

- INSIDE LAN: `10.10.10.0/24`
- DMZ LAN: `10.10.50.0/24`
- OUTSIDE/WAN: `200.1.1.0/30`
- Public NATs:
  - Web Server (DMZ): `200.1.1.50` → `10.10.50.50`
  - DNS Server (DMZ): `200.1.1.51` → `10.10.50.51`

See:
- `topology/topology-ascii.txt`
- `topology/addressing-plan.md`

---

## How to run (Packet Tracer)

1. Build the topology per `topology/topology-ascii.txt`
2. Paste each config from `configs/` into the right device
3. Configure endpoints (PCs/Servers) IPs as in the addressing plan
4. Follow `testing/test-plan.md` and take screenshots for GitHub

---

## What success looks like

From an “internet test host” (ISP loopback or an outside PC):
- ✅ Can reach **Web Server** via `http://200.1.1.50` (or ping if HTTP not simulated)
- ✅ Can query **DNS** at `200.1.1.51` (UDP/53)
- ❌ Cannot reach INSIDE LAN `10.10.10.0/24`

From INSIDE PC:
- ✅ Can browse/ping internet target (`8.8.8.8`)
- ✅ Can access DMZ servers directly (`10.10.50.50`, `10.10.50.51`)

---

## Repo structure

- `configs/` — Router + switch configs
- `security/` — ZBF policy + NAT publishing explained
- `testing/` — verification commands + test plan
- `topology/` — addressing plan + inventory + topology

---

## Author

Guively Noel — Cisco Networking / Security lab portfolio
