# installation of mysql server, firewall settings all are same as master server

# Taking backup from master server backup
`mysql -e "show schemas"`
`mysql -e "create database db1"`
`mysql db1 < db1.sql`

# mysql slave configuration 
# configuration in done in /etc/my.cnf file

# restarting mariadb process
`systemctl restart mariadb`

# listing mariadb process
`systemctl status mariadb -l`

# checking logs of mariadb process
`less /var/log/mariadb/mariadb.log`

# configure master server credentials to slaver server node
