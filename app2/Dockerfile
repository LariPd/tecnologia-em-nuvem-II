#usa a imagem oficial do PHP com apache
FROM php:8.2-apache

#porta usada pelpo remder
ENV PORT=8080

#ativa o mod_rewrite para URLs amigaveis
RUN a2enmod rewrite

# copia o código da aplicação
COPY . /var/www/html/

# corrige permissôes
RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html

# corrige configuração da porta
RUN sed -i "s/Listen 80/Listen ${PORT}/" /etc/apache2/ports.conf && \
    sed -i "s/<VirtualHost \*:80>/<VirtualHost \*:${PORT}>/" /etc/apache2/sites-available/000-defaut.conf

    #permite acesso ao diretório
    RUN echo '
