FROM nginx:latest
LABEL maintainer="Ulrich MONJI"
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y curl && \
    apt-get install -y git && \
    rm -Rf /usr/share/nginx/html/* && \
    git clone https://github.com/diranetafen/static-website-example.git /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
CMD sed -i -e 's/$PORT/'"$PORT"'/g' /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'
