FROM debian 
#FROM = Em qual imagem vou me basear para criar essa nova imagem de container

RUN apt-get update && apt-get install -y apache2 && apt-get clean
#RUN = É um parâmetro que solicita a execução de determinado comando, DURANTE a "buildagem" do container

 ENV APACHE_LOCK_DIR="var/lock"
 ENV APACHE_PID_FILE="/var/run/apache2.pid"
 ENV APACHE_RUN_USER="www-data"
 ENV APACHE_RUN_GROUP="www-data"
 ENV APACHE_LOG_DIR="/var/log/apache2"
 #ENV = Cria variavel de ambiente no container no momento que a imagem está sendo buildada

 LABEL description="Webserver"
 #LABEL = cria uma estrutura de chave e valor onde podemos colocar informações uteis, como por exemplo a informação que irei adicionar abaixo:
 LABEL version="1.0.0"

 VOLUME /var/www/html
 #VOLUME = irá criar um volume automaticamente(o docker irá criar com um nome aleatorio) - NÃO É POSSIVEL CRIAR UM VOLUME DO TIPO BIND NO DOCKERFILE
 EXPOSE 80
 #EXPOSE = o container quando criado iá expor a porta 80 

 