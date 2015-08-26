FROM ubuntu

MAINTAINER joe@avenerios.com

RUN apt-get update
RUN apt-get install -y nginx
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log
RUN rm -rf /etc/nginx/sites-enabled/default

CMD ["nginx", "-g", "daemon off;"]