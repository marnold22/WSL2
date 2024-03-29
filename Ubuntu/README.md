# UBUNTU

## Specifications & Other Notes

1. Change the hostname from `marnold@DESKTOP-QHEH3D4` to `UBUNTU` or whatever other hostname you want
    > hostname
    > sudo nano /etc/wsl.conf

        ```
        [network]
        hostname = UBUNTU
        generateHosts = false
        ```

2. Replace all instances of `DESKTOP-QHEH3D4` with `UBUNTU` or whatever other hostname you want in the /etc/hosts file
    > sudo nano /etc/hosts

        ```
        127.0.1.1       DESKTOP-QHEH3D4.localdomain     DESKTOP-QHEH3D4
        ```

        ```
        127.0.1.1       UBUNTU.localdomain     UBUNTU
        ```

## Install LAMP Stack

1. APACHE
    > sudo apt install apache2
    1. VirtualHosts File Config
       1. > sudo touch localhost.conf
       2. > sudo nano localhost.conf
                ```text
                    <VirtualHost *:80>
                        ServerName localhost
                        DocumentRoot /var/www/html/
                    </VirtualHost>

                    <VirtualHost *:80>
                        ServerName info.localhost
                        DocumentRoot /var/www/info.local/
                    </VirtualHost>

                    <VirtualHost *:80>
                        ServerName vingroup.localhost
                        DocumentRoot /var/www/vingroup.local/vingroupcpa/
                    </VirtualHost>

                    <VirtualHost *:80>
                        ServerName vaphotos.localhost
                        DocumentRoot /var/www/vaphotos.local/vaphotos/
                    </VirtualHost>
                ```
    2. Add to /etc/hosts file

            ```text
                127.0.0.1       localhost
                127.0.0.1       info.localhost
                127.0.0.1       vingroup.localhost
                127.0.0.1       vaphotos.localhost
                127.0.0.1       [OTHER_SITES_HERE].localhost
            ```

    3. Add /etc/wsl.conf

            ```text
                # Network host settings that enable the DNS server used by WSL 2. This example changes the hostname, sets generateHosts to false, preventing WSL from the default behavior of auto-generating /etc/hosts, and sets generateResolvConf to false, preventing WSL from auto-generating /etc/resolv.conf, so that you can create your own (ie. nameserver 1.1.1.1).
                [network]
                generateHosts = false
            ```

2. PHP
    > sudo apt install php libapache2-mod-php
    > sudo apt install php-curl php-gd php-json php-mbstring php-xml
    > sudo nano /etc/apache2/mods-enabled/dir.conf

        ```
        <IfModule mod_dir.c>
            DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
        </IfModule>
        ```

3. MYSQL
    > sudo apt install mysql-server php-mysql
    > sudo service mysql restart
        #> Validate password component: N
        #> New password: password
        #> Remove anonymous users: Y
        #> Disallow root login remotely: Y
        #> Reload privilege tables now: Y
    > sudo service mysql stop
    > sudo usermod -d /var/lib/mysql mysql
    > sudo service mysql start

4. Allow Remote root Login
    > sudo mysql -u root -ppassword  -e "UPDATE mysql.user SET plugin = 'mysql_native_password' WHERE User = 'root'; FLUSH PRIVILEGES;"

5. PHPMYADMIN
    > sudo apt install phpmyadmin
        #> Use apache2
        #> Configure db with dbconfig-common: Yes
        #> Random password (leave password blank)
    > sudo mysql -u root

    mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;
    mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
    mysql> FLUSH PRIVILEGES;
    mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;
    mysql> CREATE USER 'marnold'@'localhost' IDENTIFIED BY 'password';
    mysql> GRANT ALL PRIVILEGES ON *.* TO 'marnold'@'localhost' WITH GRANT OPTION;
    mysql> exit

## Original Commands

> sudo service apache2 start
> sudo service mysql start
> sudo service apache2 restart
> sudo service mysql restart
> sudo service apache2 stop
> sudo service mysql stop

## Custom Commands

> touch .bash_aliases
> echo 'alias lampstatus="sudo service apache2 status ; sudo service mysql status"' >> .bash_aliases
> echo 'alias lampstart="sudo service mysql start ; sudo service apache2 start"' >> .bash_aliases
> echo 'alias lampstop="sudo service mysql stop ; sudo service apache2 stop"' >> .bash_aliases
> echo 'alias lamprestart="lampstop ; lampstart"' >> .bash_aliases
