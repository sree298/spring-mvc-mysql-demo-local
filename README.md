## Tomcat9
# spring-mvc-mysql-demo-local
1. **Build the WAR** 
```bash
cd spring-mvc-mysql-demo-local
mvn clean package
```
```bash
mysql -u demo_user -p
Enter password: demo123
OR
mysql -u demo_user -pdemo123
mysql> show databases;
mysql> use demo_db;
mysql> show tables;
```
```bash
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(50),
  age INT
);


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
```bash
http://localhost:8081/spring-mvc-mysql-demo-local
```
