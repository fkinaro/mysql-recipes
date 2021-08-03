# Installing MySQL/Mariadb
- Update your system first: 
```shell
sudo apt-get update
sudo apt-get install mariadb
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
