# XAMPP 5.6.40 Docker Container

This is a Docker container for XAMPP 5.6.40. 
This is a custom image that is built on debian:buster.
XAMPP is installed from the official source. https://www.apachefriends.org/index.html 

## Usage
1. Clone this repository
2. Run `docker-compose up -d`
3. Open http://localhost:80/dashboard/ in your browser
This will open the XAMPP dashboard.
4. Click on phpmyadmin or http://localhost/phpmyadmin/ to open phpmyadmin

## Passwords
 Both MySQL and phpmyadmin use default XAMPP password.

## Ports
The following ports are exposed by default. This is based on the docer-compose file. You can change the ports in the docker-compose file.
- 80
- 443
- 3306

Port 80 is used for the web server. 
Port 443 is used for the SSL web server. 
Port 3306 is used for MySQL.

## Volumes
The www folder is mounted to the host machine. This is where you can put your web files. 

## SSH XAMPP Server
You can SSH into the XAMPP server by running 
```
ssh root@localhost
```
The default password is `root`
    
## XAMPP Commands And using MySql from the command line
1. SSH into the XAMPP server by running `ssh root@localhost` or docker exec -ti xampp-server bash
2. export PATH=/opt/lampp/bin:$PATH
This will add the XAMPP bin folder to the path so you can run XAMPP commands.

## Restarting XAMPP
Run the restart.sh script to restart XAMPP. This is useful if you make changes to the XAMPP configuration files. or 
```
docker exec myXampp /opt/lampp/lampp restart
```

