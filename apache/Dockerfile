ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
  apk upgrade;

# Copy apache vhost file to proxy php requests to php-fpm container
COPY phpback.apache.conf /usr/local/apache2/conf/phpback.apache.conf
RUN echo "Include /usr/local/apache2/conf/phpback.apache.conf" \
  >> /usr/local/apache2/conf/httpd.conf