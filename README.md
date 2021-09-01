![Screenshot from 2021-09-01 23-20-41](https://user-images.githubusercontent.com/89920650/131719605-4b7c550c-7fc8-4bee-89f2-999f913b750f.png)
# MT19AIE298

Question No. 2


Step 1 : Install docker package in our system.

Step 2:  Pull ubuntu image ( $ docker pull ubuntu ) this docker image around 75MB. 

Step 3:  Run ubuntu contaner ( $ docker run -it ubuntu )

Step 4: Install webserver , database server,  PHP , IP package and ssh service.
                  $ apt update
                  $ apt install apache2  mysql-server  install php  php-mysql  iproute2 openssh-server

Step 5: Add "ServerName localhost" in file  /etc/apache2/apache2.conf

Step 6: Restart mysql and apache service 
             $ service apache2 restart
             $ service mysql restart

Step 7: Deploy web application in folder /var/www/html/ .
            $ scp -r rimpesh@10.1.11.130:~/Downloads/php-crud/ .


Step 8: Create Schema and tables in mysql database.

            $ mysql -u root -p

                     > create database crud;
                     > CREATE USER 'mt19aie210'@'%' IDENTIFIED BY 'admin';
                     >GRANT ALL PRIVILEGES ON crud.* TO 'mt19aie210'@'%';
                     >FLUSH PRIVILEGES;

           $ mysql -u mt19aie210 -p

                     >show databases;
                     >  use crud;

                     > CREATE TABLE IF NOT EXISTS `crud`.`users` (
                            `userId` int(8) NOT NULL,
                            `userName` varchar(55) NOT NULL,
                            `password` varchar(55) NOT NULL,
                            `firstName` varchar(255) NOT NULL,
                            `lastName` varchar(255) NOT NULL
                         );
Step 9: Once webserver and application deployed check the IP of the container.
              $ ip address show

Step 10: By this IP we can run the applicaion in browser. 
