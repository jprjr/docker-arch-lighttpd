# jprjr/lighttpd

This is an Arch Linux-based image with [lighttpd](http://www.lighttpd.net/) installed.

## Usage

Mount a volume with your lighttpd config - I have an example in this github
repo under the `example-conf` directory for proxying a fastcgi app.

### Build

```
$ docker build -t <repo name> .
```

### Run in foreground

```
$ docker run -v /path/to/conf:/etc/lighttpd -p 80 jprjr/lighttpd
```

### Run in background

```
$ docker run -d -v /path/to/conf:/etc/lighttpd -p 80 jprjr/lighttpd
```

### Run a PHP app

```
$ docker run -d --name test_app jprjr/php-fpm
$ docker run -d --link test_app:fastcgi --volumes-from test_app \
  -p 80:80 -v /path/to/example-conf:/etc/lighttpd jprjr/lighttpd
```

Hit port 80 and you should see the output of phpinfo().

## Exposed ports

* 80, 443

## Exposed volumes

* `/etc/lighttpd` 
