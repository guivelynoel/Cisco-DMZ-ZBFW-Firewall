
# NAT Publishing (Static NAT) + PAT

## Static NAT (DMZ services)
We map internal DMZ IPs to public IPs:

- Web: `10.10.50.50` → `200.1.1.50`
- DNS: `10.10.50.51` → `200.1.1.51`

This allows the internet to reach the servers *only* if the firewall permits it.

## PAT (Inside users to internet)
Inside PC `10.10.10.10` can reach internet using overload on the outside interface.
