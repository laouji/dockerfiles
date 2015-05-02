FROM ubuntu

MAINTAINER laouji

RUN echo "deb http://archive.ubuntu.com/ubuntu/ raring main universe" >> /etc/apt/sources.list

RUN mv /etc/apt/sources.list /etc/apt/_sources.list.bk
ADD sources.list /etc/apt/
RUN apt-get update
RUN apt-get install -y vim wget dialog net-tools
RUN apt-get install -y nginx

RUN mv /etc/nginx/nginx.conf /etc/nginx/_nginx.conf.bk
ADD nginx.conf /etc/nginx/

ADD default.conf /etc/nginx/conf.d/

EXPOSE 80

CMD service nginx start
