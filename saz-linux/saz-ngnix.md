# saz-ngnix

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/ngnix


## ngnix - Installer certificat SSL
```
  #### 1 : You need to merge the *.pem file into the *.crt file.

  #### Find the certificate files in vHost
  cd  /etc/nginx/sites-enabled/
  nano my.domaine.com.conf
    ssl_certificate /etc/ssl/_my.domaine.com/_my.domaine.com.pem;
    ssl_certificate_key /etc/ssl/_my.domain.com/_my.domain.com.key;

  #### 2 : Integrate the PEM file into CRT 
  cat GandiStandardSSLCA2.pem >> _my.domain.com.crt

  #### 3 : Restart the ngnix service
  service nginx restart

  #### 4 :  Check certificate date :
  openssl x509 -in *.crt -text -noout
```


