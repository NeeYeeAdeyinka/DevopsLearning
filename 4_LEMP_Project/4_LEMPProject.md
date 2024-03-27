# Documenting the DareyIO LEMP Stack Learning Project

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

### Installing nginx
![Install apache2](./imgs/5.png)

### Alas prior apache install already locked down port 80 so I verified port 80 was in use with the sudo ss command and then freed up the port by stopping and disabling apache2
![Fix issues with nginx install](./imgs/6.png)


### Check that nginx was successfully installed using the systemctl command to start it and check status
![check nginx install status](./imgs/7.png)

### Use curl to view the default index.html file being served up from my localhost / 127.0.0.1:80
![Curl](./imgs/8.png)

### Check that the nginx web server is up and running using http
![web page](./imgs/9.png)

### Install mysql database server
![MySQL](./imgs/10.png)

### Secure mysql database server
![Secure](./imgs/11.png)
![Secure and lock down](./imgs/12.png)
![Secure and lock down](./imgs/13.png)

### Installing php and other key php modules
![PHP](./imgs/14.png)

### Make a new directory under /var/www for my LEMP Project - critical to grant permissions to the folder (ideally parent) using the chown -R $USER:$USER /var/www cmd
![setup project folder](./imgs/15.png)

### Setup a basic ServerBlock (VirtualHost in apache2) Config under /etc/nginx/sites-available - this will be a .conf file. Also setup symlinks and other house keeping with '$ sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/' and 'sudo unlink /etc/nginx/sites-enabled/default'
![Server Block](./imgs/16.png)
![Server Block](./imgs/17.png)
![Server Block](./imgs/18.png)

### Test that my new site works by editing the /var/www/projectLEMP/index.html file - basically setup a basic static webpage - prettied up the formatting a bit in nano text editor.
![Test that new site is up](./imgs/19.png)
![Test that new site is up](./imgs/20.png)

### Test that my index.php file at the /var/www/projectLEMP directory works - by default a .html file is loaded ahead of a .php file
![test .php functionality](./imgs/21.png)
![test .php functionality](./imgs/22.png)

### Prepared to integrate php with mysql and serve it up on nginx webserver
**Logged into mysql as root and then created a new DB 'MyTestDB' and new user 'TestDBUser' - weakpassword did not work :)**
![Login to my sql](./imgs/23.png)
![create TestDB and TestDBUser](./imgs/24.png)

**Logged into mysql as 'TestDBUser' and created new table within the DB - ran into some syntax errors with the SQL statements but figured it out**
![](./imgs/25.png)
![](./imgs/26.png)
![](./imgs/27.png)

**Needed to do quite a lot of custom mods to get my php script to work - apparently using special characters '@' & '$' in the TestDBuser password caused trouble - found this out in /var/log/nginx/error.log**
**Did not work!!!**
![](./imgs/28.png)
**Worked!!!** but needed me to relax the password policy with mysql> SET GLOBAL validate_password.policy = 0; after checking the policy in force with mysql> SHOW VARIABLES LIKE 'validate_password%'
![](./imgs/29.png)
##### Needed to associate TestDBUser specifically with localhost and my windows PC IP - need to investigate this further
![](./imgs/30.png)

### Finally success smiled at me after almost 9 hours of struggles :)
![](./imgs/31.png)







