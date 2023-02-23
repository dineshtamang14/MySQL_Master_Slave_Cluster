# creating a sample database in master mysql node
`show schemas;`

`create database db1;`
`use db1;`

# creating sample table
`create table db1tb1(name varchar(10));`
`insert into db1.db1tb1 values('India');`


# configuration in master node inorder to make it master node
`vim /etc/my.cnf`

# to login to mysql server without password create this file .my.cnf in working directory
`vim ~/.my.cnf`


# setting up replication for slave server
`mysql`
`grant replication slave on *.* to user@'slave-server-ip' identified by 'user';`

`flush privileges;`

# changing table permission to read only
`flush tables with read lock;`

# To list the master status
`systemctl restart mariadb`
`mysql`
`show master status;`

# creating a backup from master database
`mysqldump db1 > db1.sql;`

# copying backup to slave server
`scp db1.sql slaver-server-ip:/root/`

# to unlock read only table
`unlock tables;`

# To see master status
`show master status\g;`