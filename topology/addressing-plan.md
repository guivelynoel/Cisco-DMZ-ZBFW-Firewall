
# Addressing Plan

## OUTSIDE (WAN)
- ISP-R1 G0/0: `200.1.1.1/30`
- EDGE-R1 G0/0: `200.1.1.2/30`
- Default route on EDGE-R1 → `200.1.1.1`

## INSIDE LAN
- Network: `10.10.10.0/24`
- EDGE-R1 G0/1: `10.10.10.1`
- Inside-PC: `10.10.10.10` (GW: 10.10.10.1)
- INSIDE-SW1 mgmt (optional): `10.10.10.2` (GW: 10.10.10.1)

## DMZ LAN
- Network: `10.10.50.0/24`
- EDGE-R1 G0/2: `10.10.50.1`
- Web Server: `10.10.50.50` (GW: 10.10.50.1)
- DNS Server: `10.10.50.51` (GW: 10.10.50.1)
- DMZ-SW1 mgmt (optional): `10.10.50.2` (GW: 10.10.50.1)

## Internet Simulation
- ISP-R1 Loopback0: `8.8.8.8/32`

## Static NAT (publish DMZ servers)
- `200.1.1.50` ↔ `10.10.50.50` (Web)
- `200.1.1.51` ↔ `10.10.50.51` (DNS)
