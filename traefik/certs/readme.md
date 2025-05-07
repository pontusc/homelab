Information about my self-signed certs

# Gen base key
openssl genrsa -out <KEYNAME.key> 4096

# Gen cert
openssl req -new -x509 -sha256 -days 10950 -key <KEYNAME.key> -out <CERTNAME.crt> -utf8

# Base64 encode cert and key, paste into the cert-secret-template
cat <CERTNAME.crt> | base64 -w 0
