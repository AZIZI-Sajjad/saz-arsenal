# saz-linux-letsEncrypt

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux-letsEncrypt

## Linux LetsEncrypt - install Debian
```
sudo apt-get update; sudo apt-get install certbot python3-certbot-apache
```

## Linux LetsEncrypt - Generate Certificate SSL for a domaine - With Apache validation Methode
```
letsencrypt --apache -d <Domaine> --agree-tos
```
