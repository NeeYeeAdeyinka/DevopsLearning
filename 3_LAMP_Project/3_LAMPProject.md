# Documenting the DareyIO LAMP Stack Learning Project

### Setting up my prerequisites - AWS User Account etc
![Basics](./imgs/0.png)

### Setting up a test server on AWS to play with - EC2 t2.micro
![Set up virtual server on AWS](./imgs/1.png)

### Setting inbound rules to permit ssh, http and https on the EC2 t2.micro
![Inbound rules](./imgs/2.png)

### Connecting to the remote EC2 t2.micro server from my local machine
![Connect and login](./imgs/3.png)

### Bring the server up to date
![Update server software](./imgs/4.png)

### Installing apache2
![Install apache2](./imgs/5.png)
![Install apache2](./imgs/6.png)

### Check that apache2 was successfully installed using the systemctl command
![check apache2 install status](./imgs/7.png)

### Use curl to view the default index.html file being served up from my localhost / 127.0.0.1:80
![Curl](./imgs/8.png)

### Check that the apache2 web server is up and running using http
![web page](./imgs/9.png)

### Install mysql database server
![MySQL](./imgs/10.png)

### Secure mysql database server
![Secure](./imgs/11.png)
![Secure and lock down](./imgs/12.png)
![Secure and lock down](./imgs/13.png)

### Installing php and other key php modules
![PHP](./imgs/14.png)

### Test that php is installed and version
![Test PHP](./imgs/15.png)

### Make a new directory under /var/www for my LAMP Project - critical to grant permissions to the folder (ideally parent) using the chown -R $USER:$USER /var/www cmd
![setup project folder](./imgs/16.png)

### Setup a basic VirtualHost Config under /etc/apache2/sites-available - this will be a .conf file
![Virtual Host](./imgs/17.png)
![Virtual Host](./imgs/18.png)

### Enable my newly created site by running a2ensite on the newly created .conf at /etc/apache2/sites-available and disabling the 000-deafult.conf site
![Enable .conf for site](./imgs/19.png)

### Test that my new site works by editing the /var/www/projectlamp/index.html file - basically setup a basic static webpage
![Test that new site is up](./imgs/20.png)

### Test that my index.php file at the /var/www/projectlamp directory works - by default a .html file is loaded ahead of a .php file
![test .php functionality](./imgs/21.png)
![test .php functionality](./imgs/22.png)







