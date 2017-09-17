FROM projectdc/base

MAINTAINER ysicing

ADD  nginx.list /etc/apt/sources.list

#RUN curl https://nginx.org/keys/nginx_signing.key | apt-key add -  

RUN  apt-get update && \
    apt-get install -y nginx nginx-extras

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

ADD nginx.conf /etc/nginx/nginx.conf

COPY default.conf /etc/nginx/conf.d/default.conf
COPY ssl/* /etc/nginx/conf.d/ssl/


EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
