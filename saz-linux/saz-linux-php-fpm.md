# saz-linux-php-fpm

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux-php-fpm

## Linux - php-fpm activate logging
```
    ### 1- Go to config DIR: 
        cd /etc/php/7.4/fpm/pool.d
    ### 2- Open Config File:
        nano www.conf
    ### 3- Uncomment the following line :
         php_admin_value[error_log] = /var/log/fpm-php.www.log
    ### 4- Restart PHP-FPM Service:
        service php7.4-fpm restart
    ### 5- Check PHP-FPM Service:
        service php7.4-fpm restart
```
