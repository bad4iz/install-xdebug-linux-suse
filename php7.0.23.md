# install-xdebug-linux-suse  
установка xdebug на линукс в частности opensuse и xampp   

## Собираем Xdebug 
`$ git clone git://github.com/xdebug/xdebug.git`

`$ cd xdebug*`

`$ phpize`

`$ ./configure --enable-xdebug`

`$ make`

## Копируем в папку к Ксампу

`$ sudo cp modules/xdebug.so /opt/lampp/lib/php/extensions/`

## Конфигурируем PHP
прописываем в `/opt/lampp/etc/php.ini`   
Включаем библиотеку (я добавил это на 545 строке) можно в конце
`zend_extension="/opt/lampp/lib/php/extensions/xdebug.so"`

## Запуск/перезапуск и проверка

`$ sudo /opt/lampp/lampp restart`

`$ /opt/lampp/bin/php -i | grep xdebug`
вывод 
```
xdebug
xdebug support => enabled
xdebug.auto_trace => Off => Off
xdebug.collect_includes => On => On
xdebug.collect_params => 0 => 0
xdebug.collect_return => Off => Off
xdebug.collect_vars => Off => Off
xdebug.default_enable => On => On
xdebug.dump.COOKIE => no value => no value
xdebug.dump.ENV => no value => no value
...
и т.д.

```

