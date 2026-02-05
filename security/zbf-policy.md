
# Zone-Based Firewall (ZBF) — Policy Summary

ZBF works with **zones** and **zone-pairs**:
- You put interfaces into zones (INSIDE, DMZ, OUTSIDE)
- You define zone-pairs (source-zone → destination-zone)
- You attach a policy-map to each zone-pair
- Only what you allow is permitted

## Zone rules in this project

### OUTSIDE → INSIDE
- **DROP** (block everything)

### OUTSIDE → DMZ
- Allow only:
  - HTTP (tcp/80) to public web NAT
  - HTTPS (tcp/443) to public web NAT
  - DNS (udp/53 + tcp/53) to public DNS NAT
- Everything else DROP

### INSIDE → OUTSIDE
- Allow ALL (stateful return traffic permitted automatically)

### INSIDE → DMZ
- Allow ALL (common enterprise requirement for app/admin access)

### DMZ → INSIDE
- DROP (DMZ servers should not initiate to inside)
