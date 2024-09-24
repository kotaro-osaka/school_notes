---
tags:
  - "#outdated"
  - half_duplex
---
# CSMA
> Carrier-Sense Multiple Access
- Used to avoid collisions in shared communication channels
- **Carrier-Sense**: Devices listen to medium to check for existing transmissions
- **Multiple Access**: Multiple devices can attempt to transmit
## CSMA/CD
> CSMA with Collision Detection
- Early ethernet networks
- Detects collisions
**Collision Detected**
1. All transmission is stopped by jamming signal
2. Transmission from collision parties resumed after random amount of time
## CSMA/CA
> CSMA with Collision Avoidance
- Wireless networks
- Tries to avoid collisions
- Waits for clear medium before transmitting
or
- Uses [[#RTS/CTS]] to coordinate transmissions
### RTS/CTS
> Request to Send
> Clear to Send
1. Request (RTS) sent to access point
2. Access point stops all communications on network
3. Response (CTS) - Permission to send
- RTS frame includes `duration of transmission`, `frame size`