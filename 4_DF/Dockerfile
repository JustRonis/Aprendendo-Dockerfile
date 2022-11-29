# AJUSTES NO 3_DF

FROM debian 

RUN apt-get update && apt-get install -y apache2 && apt-get clean

ENV APACHE_LOCK_DIR="var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

COPY index.html /var/www/html/

LABEL description="Webserver"
LABEL version="1.0.0"

USER root
#dado que não conseguimos bindar uma porta baixa sem ser root, precisamos de fato usar o root neste caso. Normalmente por default o usuario seria o root, mas vou deixar explicito pq sim

WORKDIR /var/www/html

VOLUME /var/www/html/

EXPOSE 80

ENTRYPOINT [ "/usr/sbin/apachectl" ]

CMD ["-D", "FOREGROUND"]
 