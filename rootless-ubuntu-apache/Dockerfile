FROM ubuntu:18.04
WORKDIR /var/www/html
EXPOSE 80
ADD . .
RUN apt-get update && apt-get install -y \
    perl \
    apache2 \
    sudo
RUN adduser --disabled-password \
    --gecos '' docker \
    && adduser docker sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:/usr/sbin/apache2ctl' >> \
    /etc/sudoers
USER docker
CMD sudo /usr/sbin/apache2ctl -D FOREGROUND 