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


## Exposed ports

* 80, 443

## Exposed volumes

* `/etc/lighttpd` 
