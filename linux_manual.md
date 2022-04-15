## 写在前面

- 此教程专为有洁癖的宝宝们准备。不使用任何一键安装脚本。面板党可以退散了！！
- 本人测试环境是 Debian 11 其他的没测试。
## 手动安装lnmp
- 更新源

```bash  
apt update  
apt upgrade
``` 

- 安装Nginx
```bash
apt install nginx
```
- 安装Mariadb
```bash
apt install mariadb-server
```
- 配置Mariadb
```bash
mysql_secure_installation
```
根据提示操作即可。
- 创建数据库
```bash
mariadb
```
之后会显示
```bash
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 74
Server version: 10.3.15-MariaDB-1 Debian 10

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> 
```
接下来输入命令 
```sql
CREATE DATABASE [这里替换为数据库名] ;
GRANT ALL ON [这里替换为数据库名].* TO '[这里替换为用户名]'@'localhost' IDENTIFIED BY '[这里替换为密码]' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT
```
- 安装PHP7.4
```bash
apt install php php-fpm php-mysql php-gd php-zip php-opcache php-curl php-mbstring php-intl php-dom php-bcmath php-redis php-fileinfo
```
- 安装redis
```bash
apt install redis
```
