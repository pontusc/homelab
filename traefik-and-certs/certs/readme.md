# Certificates

Wildcard cert is populated using cert-manager and cloudflare dns0 challenge.

# Information about self-signed certs -- BELOW IS NOT IN USE

Gen base key
`openssl genrsa -out <KEYNAME.key> 4096`

Gen cert
`openssl req -new -x509 -sha256 -days 10950 -key <KEYNAME.key> -out <CERTNAME.crt> -utf8`

Base64 encode cert and key, paste into the cert-secret-template
`cat <CERTNAME.crt> | base64 -w 0`
