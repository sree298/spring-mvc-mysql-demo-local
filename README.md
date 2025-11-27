```bash
mysql -u demo_user -p
Enter password: demo123
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
