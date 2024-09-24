# SMTP
___
> Simple Mail Transfer Protocol
- Used for sending / receiving messages between servers
- Port `25`
- Text-based (commands / responses transmitted as plain text) 
## Sending Email
1. Client communicates with SMTP server
2. Client sends email to SMTP server using SMTP commands
3. Server processes email & routs to destination server
## Receiving Email
1. Sender's email server communicates with receiver's email server using SMTP
2. Receiver's email server receives & stores email until inbox is checked
## Ports
- `143` (unencrypted)
- `995` (encrypted over `TLS/SSL` SMTP with STARTTLS)