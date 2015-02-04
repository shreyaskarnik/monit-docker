# Dockerized Monit

Clone this repo. 

Edit [monitrc](http://mmonit.com/monit/documentation/monit.html#THE-MONIT-CONTROL-FILE) to set your monit config.

Add Configuration for Services/Process that you want to monitor in conf.d

For example, nginx monitoring can be added in conf.d as

```
check process nginx with pidfile /var/run/nginx.pid
    start program = "/etc/init.d/nginx start"
    stop program = "/etc/init.d/nginx stop"
```

Build Docker Image ```docker build -t <mymonit> .```

Monit Image is ready and can be invoked as ```docker run -d -p 2812:2812 <mymonit>```

Monit is now running and is available at <host-ip>:2812 