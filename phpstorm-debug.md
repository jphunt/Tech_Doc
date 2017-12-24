# PhpStorm Debug

## XDebug
### installation
brew install php71-xdebug

### Enable xdebug
```
php -i
php -v

vi ext-xdebug.ini
```

Add following lines:
```
xdebug.remote_enable=1
xdebug.remote_connect_back=1
```

### Install chrome plugin and enable plugin
Xdebug helper

### From PhpStorm enable "start listening from connection"


