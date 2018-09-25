# ELK-filebeat-nginx

## Git book version
for more detail and screenshot to set up lab.

highly recommend git book version.

please click https://ricotech.gitbook.io/ricotech/

## MAC Environment 
Because filebeat need to collect log.

But It’s not easy to find docker container location in MAC.

So I install nginx on local and set up ELK & filebeat by docker compose.

## 1. Install nginx on local

`brew install nginx`

open browser http://localhost:8080/ and refresh (command + r) it made some logs.

nginx default location in /usr/local/var/log/nginx/

`cat /usr/local/var/log/nginx/access.log`

because this lab only process nginx’s access log.
error log just ignore it.


## 2. Set up ELK by docker compose

Because docker bind mount directory need to add first.

Then nginx’s log can collect by filebeat

Add /usr/local/var/log/nginx/ in docker file sharing

`docker-compose up`


## 3. Collecting logs

make some logs. refresh (command + r) in http://localhost:8080/

And go to http://localhost:5601/

check our logs already process many fields.
