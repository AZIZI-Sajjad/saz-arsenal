# saz-node-js-pm2

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/node-js-pm2


## Node-JS pm2 - Reference:
```
https://pm2.keymetrics.io/docs/usage/log-management/
```

## Node-JS pm2 - 00 Save Configurations for next System restart ou service restart
```
pm2 save
```



## Node-JS pm2 - Restart Application
```
pm2 start <Application_front_dist_ssr_index.js> --name <Application_Firendly_Name>
        #### Exemple : pm2 start /var/www/html/cabinet-delsol/front/dist/ssr/index.js --name Cabinetdelsol
```


## Node-JS pm2 - Restart Application
```
pm2 restart <app_name>
```

## Node-JS pm2 - Reload Application
```
pm2 reload <app_name>
```

## Node-JS pm2 - Stop Application
```
pm2 stop <app_name>
```

## Node-JS pm2 - delete Application (Don't Remove Application's files and Folders) 1 
```
pm2 delete <app_name>
```

## Node-JS pm2 - delete Application (Don't Remove Application's files and Folders) 2 
```
pm2 del <app_name>
```

## Node-JS pm2 - Remove Application (Don't Remove Application's files and Folders) 3 
```
pm2 rm <app_name>
```
