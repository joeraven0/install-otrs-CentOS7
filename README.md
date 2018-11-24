# Installing OTRS-community ticket system on CentOS7 Minimal

#### 1. Install CentOS7
#### 2. Activate network
`$ nmcli d`

`$ nmtui`
[Activate network CentOS7](https://www.krizna.com/centos/setup-network-centos-7/)
#### . Autostart apache on reboot
`$ sudo systemctl enable httpd`

`$ sudo systemctl start mariadb`

#### 3. Install wget and download OTRS installation file
`$ sudo yum install wget`

`$ sudo wget 'X.X.X.X/otrs.rpm`
#### 4. Install OTRS
[OTRS6 nstallation instruction](https://doc.otrs.com/doc/manual/admin/6.0/en/html/installation.html#installation-on-centos)

#### . Configure database
`$ sudo systemctl enable mariadb`

`$ sudo systemctl start mariadb`

`$ sudo mysql -u root -p`

`> CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';`

`> CREATE DATABASE databasename DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;`

`> GRANT ALL PRIVILEGES ON databasename.* TO 'username'@'localhost' IDENTIFIED BY 'password';`

`> FLUSH PRIVILEGES;`

#### . Stop firewall and visit configure page
`$ sudo systemctl disable firewalld`

`$ sudo systemctl stop firewalld`
