FROM nginx:1.20-alpine
 
RUN apk update && apk add openssl
RUN rm /etc/nginx/conf.d/default.conf && mkdir -p /mysite/html
 
RUN openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048 &&\
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/certs/self.key -out /etc/ssl/certs/self.crt \
    -subj "/C=RU/ST=Moscow/L=Rrrrttt/O=Qqqwwww Code/OU=Org/CN=mysite.aaa"
 
COPY nginx.conf /etc/nginx/conf.d
