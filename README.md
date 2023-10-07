# Tested in Ubuntu 22.04

## Firewall

```
sudo ufw enable
```

```
sudo ufw allow 22
```

## Apache

```
sudo apt install apache2
```

```
sudo ufw allow Apache
```

```
sudo ufw allow 'Apache Full'
```

```
sudo ufw allow 'Apache Secure'
```

![My Image](./images/image1.png)

## MariaDB

```
sudo apt install mariadb-server mariadb-client
```

```
sudo mysql_secure_installation
```

![My Image](./images/image2.png)
![My Image](./images/image3.png)
![My Image](./images/image4.png)

```
sudo mysql
```

```
CREATE USER 'user'@'%' IDENTIFIED BY 'password';
```

```
GRANT ALL PRIVILEGES ON *.* TO 'user'@'%';
```

```
FLUSH PRIVILEGES;
```

```
EXIT
```

![My Image](./images/image5.png)

### Enable MariaDB Remote Access

```
sudo ufw allow 3306
```

![My Image](./images/image6.png)

```
sudo vim /etc/mysql/mariadb.conf.d/50-server.cnf
```

- From this
  ![My Image](./images/image7.png)
- To this
  ![My Image](./images/image8.png)

- Restart MariaDB

```
sudo systemctl restart mariadb.service
```

## PHP

```
sudo apt install php7.4 libapache2-mod-php7.4 php7.4-bcmath php7.4-curl php7.4-json php7.4-mbstring php7.4-mysql php7.4-tokenizer php7.4-xml php7.4-zip php7.4-cli php7.4-fpm
```

![My Image](./images/image9.png)
![My Image](./images/image10.png)

## phpMyAdmin

```
sudo apt install phpmyadmin
```

![My Image](./images/image11.png)

- Choose apache2
  ![My Image](./images/image12.png)
- Choose yes
  ![My Image](./images/image13.png)
- Input password for phpMyAdmin
  ![My Image](./images/image14.png)
  ![My Image](./images/image15.png)
- Open phpMyAdmin in browser
  ![My Image](./images/image16.png)

# Setup
```
sudo chown -R $USER:$USER /var/www/html
```
```
sudo chmod -R 755 /var/www/html
```

# CodeIgniter 3 Problem

```
sudo vim /etc/apache2/apache2.conf
```

- Change this
  ![My Image](./images/image17.png)
- To this
  ![My Image](./images/image18.png)

```
sudo systemctl restart apache2.service
```

```
sudo a2enmod rewrite
```

```
sudo systemctl restart apache2.service
```

# Laravel 9 Problem

```
sudo chmod 777 /var/www/html/laravel/storage
```

```
vim /var/www/html/laravel/index.php
```

![My Image](./images/image19.png)
