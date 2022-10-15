# My LAMP Setup on Ubuntu 22.04

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
sudo apt install php libapache2-mod-php php-mysql
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
  ![My Image](./images/image16P.png)
