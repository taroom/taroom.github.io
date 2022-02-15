# Disable Full Group By

kita bisa melakukan disable full group by dengan mengedit file

* sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf *

```
[mysqld]
...
...
sql_mode=STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION
```