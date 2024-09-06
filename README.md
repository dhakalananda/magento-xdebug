# magento-xdebug
Xdebugging Magento 2

This still hasn't been fully automated due to various errors during XDebug installations so including a manual method for now.

1. `docker compose up -d`
2. Go to Docker Desktop -> Container -> Exec
3. Enter the below commands
```bash
apt update
apt-get install autoconf
apt-get install build-essential

pecl install "xdebug"
```
4. `nano /opt/bitnami/php/etc/php.ini`
5. Add the below content in the file

```php
;[XDebug]
zend_extension = xdebug
xdebug.mode = debug
xdebug.client_host = 127.0.0.1
xdebug.client_port = 9003
xdebug.output_dir = /tmp
xdebug.remote_handler = dbgp
xdebug.idekey = VSCODE
xdebug.start_with_request = yes
```


TODO

Look for the fully automated solution by creating an appropriate Dockerfile
