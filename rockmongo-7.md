```
yum install composer

cd /var/www/html/rockmongo

 composer require alcaeus/mongo-php-adapter
 ```
 ```
 vim /var/www/html/rockmongo/index.php
 ```
 #add below line 11 or 12 before   define("ROCK_MONGO_VERSION", "1.1.7");
 ```
require_once 'vendor/autoload.php';
```
