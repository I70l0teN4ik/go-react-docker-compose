FROM nginx:alpine

RUN apk add --no-cache openssl \
    && mkdir -p /etc/nginx/ssl \
    && openssl genrsa -des3 -passout pass:NotSecure -out cert.pass.key 2048 \
    && openssl rsa -passin pass:NotSecure -in cert.pass.key -out /etc/nginx/ssl/cert.key \
    && rm cert.pass.key \
    && openssl req -new -passout pass:NotSecure -key /etc/nginx/ssl/cert.key -out /etc/nginx/ssl/cert.csr \
    -subj '/C=SS/ST=SS/L=Gotham City/O=API Platform Dev/CN=localhost' \
    && openssl x509 -req -sha256 -days 365 -in /etc/nginx/ssl/cert.csr -signkey /etc/nginx/ssl/cert.key -out /etc/nginx/ssl/cert.crt \
    && apk del openssl --quiet
