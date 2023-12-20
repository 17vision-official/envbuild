ARG NGINX_IMAGE
FROM ${NGINX_IMAGE}

COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/conf.d/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /etc/nginx/