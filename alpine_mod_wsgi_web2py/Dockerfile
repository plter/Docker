FROM xtiqin/alpine_apache_python3.7

COPY web2py_src.zip /usr/local/apache2/wsgiroot/
RUN cd /usr/local/apache2/wsgiroot/ \
    && unzip web2py_src.zip \
    && rm web2py_src.zip \
    && cp web2py/handlers/wsgihandler.py web2py/ \
    && chown -R www-data:www-data web2py \
    && chmod -R 777 web2py
COPY httpd-wsgi.conf /usr/local/apache2/conf/extra/