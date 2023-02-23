# mariadb installation
`sudo yum install mariadb-server`

# starting and enabling process 
`systemctl start mariadb`
`systemctl enable mariadb`

# Checking the running ports
`sudo yum install net-tools`
`netstat -nltp`

# allowing port number
`firewall-cmd --permanent --add-port=3306/tcp`

`firewall-cmd --get-services`

# checking mariadb service 
`firewall-cmd --get-services | grep mysql --color`

# allowing mariadb service in firewall
`firewall-cmd --permanent --add-service=mysql`

# reloading firewall
`firewall-cmd --reload`

# listing firewall rules
`firewall-cmd --list-all`

# configuration for mysql 
`mysql_secure_installation`