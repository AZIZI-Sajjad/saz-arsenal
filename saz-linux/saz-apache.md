# saz-apache

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/apache


## apache - Redirection permanent vHost HTTP & HTTPS
```
<VirtualHost *:80>
    ServerName <Domaine>
    ServerAlias www.<Domaine>
    <IfModule mod_rewrite.c>
        RewriteEngine On
        Redirect 301 / <Redirect_URL_complet>
    </IfModule>
</VirtualHost>
```


