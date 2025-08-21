---
tags:
  - tls
  - nmap
  - ssl
  - ciphers
---
# check url TLS and ciphers used
```bash
~ nmap --script ssl-enum-ciphers -p 443 example.com
Starting Nmap 7.95 ( https://nmap.org ) at 2025-08-21 17:25 CEST
Nmap scan report for example.com (10.11.12.13)
Host is up (0.12s latency).
Other addresses for example.com (not scanned): 10.11.12.14 10.11.12.15

PORT    STATE SERVICE
443/tcp open  https
| ssl-enum-ciphers: 
|   TLSv1.2: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (ecdh_x25519) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (ecdh_x25519) - A
|     compressors: 
|       NULL
|     cipher preference: server
|   TLSv1.3: 
|     ciphers: 
|       TLS_AKE_WITH_AES_128_GCM_SHA256 (ecdh_x25519) - A
|       TLS_AKE_WITH_AES_256_GCM_SHA384 (ecdh_x25519) - A
|       TLS_AKE_WITH_CHACHA20_POLY1305_SHA256 (ecdh_x25519) - A
|     cipher preference: server
|_  least strength: A

Nmap done: 1 IP address (1 host up) scanned in 3.28 seconds
```
