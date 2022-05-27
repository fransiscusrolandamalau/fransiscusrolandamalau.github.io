+++
title = "MySQL Fix Incorrect datetime value: ‘0000–00–00 00:00:00’"
date = 2022-04-01T12:31:39+07:00
draft = false
tags = ["datetime", "mysql"]
categories = ["Tips"]
meta = true
+++

## Solution :

If this is something you will encounter more often than once or twice, such as regular database synchronizations with another host or a dumped SQL file to be used more than once, then you may want to set the above SQL mode permanently to avoid the incorrect datetime value error.

In that case, simply edit your mysql.cnf options file, find the section starting with “[mysql]” (without quotes), and then after the [mysql] line add the following:

    [mysqld]
    sql_mode=

Open the mysql.cnf

    sudo nano /etc/mysql/mysql.cnf

Save the file, and restart MySQL.

    sudo service mysql restart

Thank you and hope it is useful.