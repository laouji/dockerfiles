FROM ubuntu

MAINTAINER laouji

RUN echo "deb http://archive.ubuntu.com/ubuntu/ raring main universe" >> /etc/apt/sources.list

RUN mv /etc/apt/sources.list /etc/apt/_sources.list.bk
ADD sources.list /etc/apt/
RUN apt-get update && \
    apt-get install -y ca-certificates dialog net-tools && \
    apt-get install -y nginx

RUN mv /etc/nginx/nginx.conf /etc/nginx/_nginx.conf.bk
ADD nginx.conf /etc/nginx/

RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

ADD default.conf /etc/nginx/conf.d/

EXPOSE 80 443

CMD service nginx start
