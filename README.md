# checks for updates
dnf update

# Adds Group Development Tools and Other 
dnf group install "Development Tools" -y

# Install Apache Web Server on CentOS 8
dnf install httpd httpd-tools -y
systemctl start httpd
systemctl enable httpd

# Install MySQL
dnf install mysql-server -y
systemctl start mysqld.service
systemctl enable mysqld

# Install PHP on CentOS 8/RHEL 8
dnf install php php-fpm php-mysqlnd php-opcache php-gd php-xml php-mbstring php-pear -y
systemctl start php-fpm
systemctl enable php-fpm
systemctl restart httpd
setsebool -P httpd_execmem 1

# checks for updates
dnf update
