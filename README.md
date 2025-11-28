# spring-mvc-mysql-demo-local
## Tomcat9 download
```bash
https://tomcat.apache.org/download-90.cgi
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.112/bin/apache-tomcat-9.0.112.tar.gz
tar -xvf apache-tomcat-9.0.112.tar.gz
cd apache-tomcat-9.0.112/conf
vi tomcat-users.xml
```
**add the below lines in tomcat-users.xml**
```bash
<role rolename="manager-gui"/>
<role rolename="admin-gui"/>
<user username="admin" password="admin" roles="manager-gui,admin-gui"/>
```
**Mysql confifuraion**
```bash
sudo mysql -u root  # <!-- click on enter -->
USE mysql;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
FLUSH PRIVILEGES;
EXIT;
sudo service mysql restart
sudo mysql -u root -p
OR
mysql -u demo_user -pdemo123
CREATE USER 'demo_user'@'localhost' IDENTIFIED BY 'demo123';
GRANT ALL PRIVILEGES ON *.* TO 'demo_user'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
mysql> show databases;
CREATE DATABASE demo_db;
mysql> show databases;
mysql> use demo_db;
mysql> show tables;
```
**create the users table**
```bash
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(50),
  age INT
);
```

1. **Build the WAR** 
```bash
cd spring-mvc-mysql-demo-local
mvn clean package
```
**Delete all rows but keep the table**
```bash
DELETE FROM users;
```
**Drop the table completely**
This will remove the table and all its data permanently:
```bash
DROP TABLE users;
```
**check the browser**
```bash
http://localhost:8081/spring-mvc-mysql-demo-local
```
