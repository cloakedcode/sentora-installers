dot not use

#Create rpm for mysql

<code>yum -y install gperf ncurses-devel time cmake libaio-devel</code>

warning not using root user thank you

<code>wget http://cdn.mysql.com/Downloads/MySQL-5.6/MySQL-5.6.15-1.el6.src.rpm \ </code>

<code>-P $HOME/rpmbuild/SRPMS/</code>

<code>rpmbuild --rebuild $HOME/rpmbuild/SRPMS/MySQL-5.6.15-1.el6.src.rpm</code>

#Regenerate repo

<code>createrepo --update $HOME/rpmbuild/RPMS/$(uname -m)</code>

#Install

<code>sed -i 's/enabled=1/enabled=0/g' "/etc/yum.repos.d/CentOS-Media.repo"</code>

<code>yum -y update</code>

<code>sed -i 's/enabled=0/enabled=1/g' "/etc/yum.repos.d/CentOS-Media.repo"</code>

<code>cd</code>

<code>yum -y remove mysql mysql-libs</code>

<code>yum -y update</code>

<code>yum -y install MySQL-server MySQL-client</code>

warning pacquet removed cronie crontabs cronie-anacron postfix

we will create package later this program is

result mysql --version

mysql  Ver 14.14 Distrib 5.6.15, for Linux (x86_64) using  EditLine wrapper

test mysql connexion

<code>service mysql start

chkconfig mysql on

cat /root/.mysql_secret</code>

<code># The random password set for the root user at Sat Jan 25 02:56:23 2014 (local time): hVvjKVuI

[root@vps1 ~]# mysql -u root -phVvjKVuI


Warning: Using a password on the command line interface can be insecure.


Welcome to the MySQL monitor.  Commands end with ; or \g.


Your MySQL connection id is 5


Server version: 5.6.15

Copyright (c) 2000, 2013, Oracle and/or its affiliates. All rights reserved.


Oracle is a registered trademark of Oracle Corporation and/or its


affiliates. Other names may be trademarks of their respective owners.


Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.


mysql></code>