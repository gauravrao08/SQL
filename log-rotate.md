```
[root@ip logrotate.d]# cat mysql-slow-query
/var/log/mysql/mysql-slow.log {
    daily
    dateext
    compress
    missingok
    rotate 5
    notifempty
    delaycompress
    sharedscripts
    nocopytruncate
    create 660 mysql mysql
    postrotate
       /usr/bin/mysql -pPASSWORD -e 'select @@global.slow_query_log into @sq_log_save; set global slow_query_log=off; select sleep(5); FLUSH SLOW LOGS; select sleep(10); set global slow_query_log=@sq_log_save;'
    endscript
    rotate 150
}

```
