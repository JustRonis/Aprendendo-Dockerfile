FROM debian 

RUN apt-get update && apt-get install -y apache2 && apt-get clean
RUN chown www-data:www-data /var/lock && chown www-data /var/run && chwon www-data:www-data /var/log
# o RUN acima esta dando permissao de dono para o usuario www-data para todo o diretorio www-data. Isto resolve o erro de permission denied neste caso especifico do apache

ENV APACHE_LOCK_DIR="var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

COPY index.html /var/www/html/
#COPY = Copia um arquivo, neste caso index.html(como não informei o path do arquivo, este index.html precisa estar no mesmo local que o dockerfile), e cola em /var/www/html/ dentro do container


LABEL description="Webserver"
LABEL version="1.0.0"

USER www-data
#USER = Solicitando para que o container rode com um usuário especifico, e não mais o root por padrão.

WORKDIR /var/www/html
#WORKDIR = Informando que o diretório "default" do container é /var/www/html, ou seja, quando o container subir e acessarmos ele, o diretorio inicial sera este informado

VOLUME /var/www/html/

EXPOSE 80

ENTRYPOINT [ "/usr/sbin/apachectl" ]
#ENTRYPOINT =  Define o principal processo, se este processo morrer, o container também morre
CMD ["-D", "FOREGROUND"]
 