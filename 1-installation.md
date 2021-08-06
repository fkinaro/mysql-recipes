# Installing MySQL/Mariadb
- Update your system first: 
```shell
sudo apt-get update
sudo apt-get install mariadb-server mariadb-client
```

- Mariadb is a dropin replacement for MySQL. The differences are minimal, and most of the commands can be used interchangeably.


## Process management for mysql
### 1. Start the service:
```shell
sudo systemctl start mysql.service
```


### 2. Check if the process is running:

```shell 
sudo systemctl status mysql.service
```


### 3. Stop:
```shell 
sudo systemctl stop mysql.service
```


### 4. Restart:
```shell
sudo systemclt restart mysql.service
```


### 5. Enable the service to start at boot
```shell
sudo systemctl enable mysql.service
```


## Further steps
### 1 Basic security:
Run 
```shell 
sudo mysql_secure_installation
```


- Set a password for the **root** user when prompted. This user is different from the OS root user;
- Verify that you can login. Enter the password you just set:
```shell
mysql -u root -p
```
The `-u` parameter specifies the username, and the `p` specifies that the mysql program should request password input.


### 2. Create a separate user
In the MySQL shell:
```shell 
CREATE USER 'username'@'localhost' IDENTIFIED BY 'YourP@55Here';
```
This creates a new user who can only login from `localhost`.

So far, our user has no access to any database. We want to limit him to his database only. Assuming the name of the database is projectExpo:
```shell 
GRANT ALL PRIVILEGES ON projectExpo.* to 'username'@'localhost';
FLUSH PRIVILEGES;
```
The last command reloads the privileges to apply the changes. The user can now do any operations on tables, queries and views in that database. 
The `*` denotes _all children of that database_ 


To grant privileges on all databases and all tables;
```shell 
GRANT ALL PRIVILEGES ON *.* to 'username'@'localhost';
FLUSH PRIVILEGES;
```

Never use this on a live server
