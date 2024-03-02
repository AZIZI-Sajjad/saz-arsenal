# saz-linux-letsencrypt

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux-letsencrypt

## Linux letsencrypt - generate a certificate
```
sudo letsencrypt --apache -d <mon_domaine> --agree-tosµ

```

## Linux letsencrypt - certificate files location
```
    #### Linux letsencrypt - certificate files location
cd /etc/letsencrypt/live/<mon_domaine>
cd /etc/letsencrypt/archive/<mon_domaine>
```


## Linux letsencrypt - README
```
This directory contains your keys and certificates.

`[cert name]/privkey.pem`  : the private key for your certificate.
`[cert name]/fullchain.pem`: the certificate file used in most server software.
`[cert name]/chain.pem`    : used for OCSP stapling in Nginx >=1.3.7.
`[cert name]/cert.pem`     : will break many server configurations, and should not be used
                 without reading further documentation (see link below).

WARNING: DO NOT MOVE OR RENAME THESE FILES!
         Certbot expects these files to remain in this location in order
         to function properly!

We recommend not moving these files. For more information, see the Certbot
User Guide at https://certbot.eff.org/docs/using.html#where-are-my-certificates.
```

## Linux letsencrypt - generate PFX Certificate
```
sudo openssl pkcs12 -export -out cert.pfx -inkey privkey1.pem -in cert1.pem -certfile chain1.pem
```