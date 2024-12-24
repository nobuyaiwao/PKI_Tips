# PKI_Tips
Let's put some command lines I sometime use, then sort them later :)

## Convert RSA to PEM
```bash
$ ssh-keygen -f id_rsa.pub -m 'PEM' -e
```

## Convert PEM to RSA
```bash
% ssh-keygen -i -f key_file
```

## Show remote server's certification
```bash
% openssl s_client -connect palcert-live.adyen.com:443 -showcerts
```

### Example
```
---
Certificate chain
 0 s:/CN=adyen.com
   i:/C=US/O=DigiCert, Inc./CN=GeoTrust Global TLS RSA4096 SHA256 2022 CA1
-----BEGIN CERTIFICATE-----
MIIHizCCBXOgAwIBAgIQCH/lZhwM657pcoDFdzG+3zANBgkqhkiG9w0BAQsFADBc
...
ZSdh9OSlrV94TBcIbWoL
-----END CERTIFICATE-----
 1 s:/C=US/O=DigiCert, Inc./CN=GeoTrust Global TLS RSA4096 SHA256 2022 CA1
   i:/C=US/O=DigiCert Inc/OU=www.digicert.com/CN=DigiCert Global Root CA
-----BEGIN CERTIFICATE-----
MIIFyzCCBLOgAwIBAgIQD2IvbyHC/11SH3I6HUfWLTANBgkqhkiG9w0BAQsFADBh
...
-----END CERTIFICATE-----
---
Server certificate
subject=/CN=adyen.com
issuer=/C=US/O=DigiCert, Inc./CN=GeoTrust Global TLS RSA4096 SHA256 2022 CA1
---
No client certificate CA names sent
Server Temp Key: ECDH, X25519, 253 bits
---
SSL handshake has read 22556 bytes and written 381 bytes
---
New, TLSv1/SSLv3, Cipher is AEAD-CHACHA20-POLY1305-SHA256
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : AEAD-CHACHA20-POLY1305-SHA256
    Session-ID:
    Session-ID-ctx:
    Master-Key:
    Start Time: 1704932065
    Timeout   : 7200 (sec)
    Verify return code: 0 (ok)
---
8000950272:error:1404C45C:SSL routines:ST_OK:reason(1116):/AppleInternal/Library/BuildRoots/0032d1ee-80fd-11ee-8227-6aecfccc70fe/Library/Caches/com.apple.xbs/Sources/libressl/libressl-3.3/ssl/tls13_lib.c:129:SSL alert number 116
```
