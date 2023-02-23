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
`change master to 
    master_host='master-server-ip',
    master_user='repl',
    master_password='repl',
    master_log_file='mysql-bin.000001',
    master_log_pos=245;
`
# To start slave server
`start slave;`

# To see slave status
`show slave status\G;`

# To see the process list
`mysql -e "show processlist"`

# To stop slave server
`stop slave;`