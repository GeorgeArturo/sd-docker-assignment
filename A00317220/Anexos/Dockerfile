FROM ubuntu:16.04
MAINTAINER tebannew@gmail.com	

ADD config/my_key.pub /tmp

#COnfigure repositorio
RUN apt-key add /tmp/my_key.pub && \
    rm -f /tmp/my_key.pub && \
    echo "deb http://192.168.131.11:8080/ xenial main" >  /etc/apt/sources.list && \
    chmod 777 /tmp

#Install packege
RUN apt-get clean -y
RUN apt-get update -y
RUN apt-get install postgresql -y

#Configuracion del puerto de python
#CMD service apache2 start && tail -f /var/log/apache2/access.log
EXPOSE 5432
CMD postgresql -m http.server 5432
 
