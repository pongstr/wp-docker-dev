FROM nginx:1.11-alpine

COPY ./lib/default.template /etc/nginx/conf.d/default.template
COPY ./lib/nginx.template /etc/nginx/nginx.template
COPY ./lib/wordpress.template /etc/nginx/wordpress.template

ADD ./lib/nginx.template /etc/nginx/nginx.conf
ADD ./lib/global /etc/nginx/global/

RUN mkdir -p /etc/nginx/ssl

CMD envsubst '\$PHP_FPM_SOCK \$SERVER_NAME' < \
      /etc/nginx/conf.d/default.template > /etc/nginx/conf.d/default.conf \
      
  &&  envsubst '\$PHP_FPM_SOCK \$SERVER_NAME' < \
      /etc/nginx/nginx.template > /etc/nginx/nginx.conf \

  &&  envsubst '\$PHP_FPM_SOCK \$SERVER_NAME' < \
      /etc/nginx/wordpress.template > /etc/nginx/global/wordpress.conf \

  && nginx -g 'daemon off;'
