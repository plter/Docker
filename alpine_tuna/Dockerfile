FROM alpine
RUN mv /etc/apk/repositories /etc/apk/repositories.bak
COPY repositories /etc/apk
RUN apk update