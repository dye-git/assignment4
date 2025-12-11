FROM fedora:latest

RUN dnf -y update && \
    dnf -y install tuxpaint vim httpd && \
    dnf clean all

COPY myinfo.html /var/www/html/myinfo.html

CMD ["httpd", "-D", "FOREGROUND"]

EXPOSE 80