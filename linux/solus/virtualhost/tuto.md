---
description: Comment créer un virtualhost
---

# Configuration

## 1 : Create a domain Name

* se placer dans `/etc/hosts`
* Add : `127.0.0.1 domain_name`

## 2 : Add your host to your server

* Se placer dans `/etc/httpd/conf.d`
* Create domain\_name.conf
* Add :

  ```text
  <VirtualHost *:80>
        #nom de domaine
    ServerName monsite

        #on accepte aussi le www
    #ServerAlias www.monsite
    ServerAlias monsite.fr

        #logs d'erreur
    ErrorLog /home/adrient/Documents/info/monsite.dev/logs/error.log 
        #logs de connexion
    CustomLog /home/adrient/Documents/info/monsite.dev/access.log common
        #Définition de la racine des sources php
    DocumentRoot "/home/adrient/Documents/info/monsite.dev/web"

    <Directory "/home/adrient/Documents/info/monsite.dev/web">
        Options Indexes MultiViews
           Order allow,deny
            Allow from all
            # New directive needed in Apache 2.4.3: 
           Require all granted
    </Directory>
  </VirtualHost>
  ```

### 3 : Common error

vérifier que la ligne `require all granted` est présente et décommenté dans Directory

### 4 : Erreur d'acces refusé à localhost:

Remplacer

```text
<Directory /var/www>
    Require all granted
    Order allow,deny
    Allow from all
</Directory>
```

par

```text
<Directory /var/www>
    Require all granted
</Directory>
```

