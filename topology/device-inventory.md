
# Device Inventory

## Routers
### EDGE-R1 (Perimeter Firewall Router)
- G0/0 OUTSIDE: `200.1.1.2/30`
- G0/1 INSIDE:  `10.10.10.1/24`
- G0/2 DMZ:     `10.10.50.1/24`
- Features:
  - Zone-Based Firewall (INSIDE/DMZ/OUTSIDE zones)
  - Static NAT for DMZ services
  - PAT for inside users

### ISP-R1 (Internet simulation)
- G0/0: `200.1.1.1/30`
- Loopback0: `8.8.8.8/32`

## Switches
- INSIDE-SW1 (access switch)
- DMZ-SW1 (access switch)

## Hosts/Servers
- Inside-PC: `10.10.10.10/24`
- Web Server (DMZ): `10.10.50.50/24`
- DNS Server (DMZ): `10.10.50.51/24`
