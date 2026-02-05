
# Test Plan (What to prove in screenshots)

## 1) Basic routing
- From EDGE-R1: ping `200.1.1.1`
- From EDGE-R1: ping `8.8.8.8`

## 2) Inside to Internet (PAT)
- From Inside-PC: ping `8.8.8.8`
- On EDGE-R1: `show ip nat translations`

## 3) Inside to DMZ (allowed)
- From Inside-PC: ping `10.10.50.50` and `10.10.50.51`

## 4) Outside to DMZ public services (allowed only)
- From ISP-R1: ping `200.1.1.50` (Web public IP)  (or HTTP if supported)
- From ISP-R1: ping `200.1.1.51` (DNS public IP)
- On EDGE-R1: `show policy-map type inspect zone-pair` (counters should increase)

## 5) Outside to Inside (blocked)
- From ISP-R1: ping `10.10.10.10`  → should FAIL
- From ISP-R1: ping `10.10.10.1`   → should FAIL

Upload screenshots into `screenshots/`.
