FROM ubuntu

RUN apt-get update
RUN apt-get install -y apache2

COPY ["index.html", "404.html", "/var/www/html/"]
COPY ejercicio.conf /etc/apache2/sites-availables/000-default.conf

EXPOSE 80
CMD apachectl -D FOREGROUND
