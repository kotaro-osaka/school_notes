# IMAP
___
> Internet Message Access Protocol
- Used by email clients to retrieve emails from mail server & manage them on the server
## Ports
- `143` (unencrypted)
- `993` (encrypted over `TLS/SSL` IMAPS)
## Retrieving Emails
1. Open email client
2. Client connects to email account using IMAP
3. Client communicates with mail server over IMAP
4. Client retrieves list of emails from mail server
## Managing Emails
- Emails remain stored on server
- User can manage emails through client
- Changes synchronized across all devices connected to server 
## Offline Access
- Offline accessibility allowed by caching copies of emails locally