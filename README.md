# install-xdebug-linux-suse  
установка xdebug на линукс в частности opensuse и xampp   

> что бы посмотреть подключен ли xdebug запускаем страницу с `phpinfo()` 
 
ищем там раздел с `xdebug` если нет то нет.  


1. установка   
> pecl install xdebug 

> все поставилось в конце такое    

> Build process completed successfully  
Installing '/usr/lib64/php5/extensions/xdebug.so'  
install ok: channel://pecl.php.net/xdebug-2.5.5  
configuration option "php_ini" is not set to php.ini location    
You should add "zend_extension=xdebug.so" to php.ini 

*типа я все поставил но в `php_ini` сам запиши*    
**прописываем в** `/opt/lampp/etc/php.ini`    

```; XDebug configuration  
zend_extension=/usr/lib64/php5/extensions/xdebug.so   
[XDebug]  
xdebug.remote_enable = 1  
xdebug.remote_autostart = 1```  

перезапускаем `sudo /opt/lampp/lampp restart` 
----------
не помогло   

да судя по информации при установки видим что `xdebug.so`лежит по `/usr/lib64/php5/extensions/xdebug.so`  
## шаг №2  
копируем файлик в `/opt/lampp/lib/php/extensions` меняем в `php_ini` на следующее  
`
; XDebug configuration  
zend_extension=/opt/lampp/lib/php/extensions/xdebug.so  
[XDebug]  
xdebug.remote_enable = 1  
xdebug.remote_autostart = 1`  

перезапускаем `sudo /opt/lampp/lampp restart` 
---------------
не помогло    

## шаг №3   
меняем в `php_ini` на следующее  

`; XDebug configuration  
zend_extension=xdebug.so  
[XDebug]  
xdebug.remote_enable = 1  
xdebug.remote_autostart = 1`  

перезапускаем `sudo /opt/lampp/lampp restart` *и вуаля все работает*    
