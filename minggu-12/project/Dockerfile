FROM nginx:1.17.2-alpine
RUN rm -rf /etc/nginx/nginx.conf /etc/nginx/conf.d
RUN mkdir -p /etc/nginx/sites-enabled
COPY nginx.conf /etc/nginx/nginx.conf
COPY conf.d /etc/nginx/conf.d
COPY sites-available /etc/nginx/sites-enabled
COPY html /usr/share/nginx/html

EXPOSE 8080
CMD ["nginx", "-g", "daemon off;"]
