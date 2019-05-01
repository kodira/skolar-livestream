FROM nginx:1.15

WORKDIR /opt/www

RUN rm -rf /etc/nginx

COPY nginx /etc/nginx
COPY html/* .

EXPOSE 80
CMD nginx


