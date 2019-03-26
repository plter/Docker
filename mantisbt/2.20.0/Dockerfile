FROM xtiqin/xampp

ENV MANTISBT_VERSION=2.20.0
WORKDIR /opt/lampp/htdocs/

RUN wget https://jaist.dl.sourceforge.net/project/mantisbt/mantis-stable/${MANTISBT_VERSION}/mantisbt-${MANTISBT_VERSION}.tar.gz
RUN tar -xzvf mantisbt-${MANTISBT_VERSION}.tar.gz \
    && mv mantisbt-${MANTISBT_VERSION} mantisbt \
    && chmod -R 777 /opt/lampp/htdocs/mantisbt/ \
    && rm mantisbt-${MANTISBT_VERSION}.tar.gz

COPY config_inc.php /opt/lampp/htdocs/mantisbt/config/

COPY bugtracker.sql /opt/
COPY init_db.sh /opt/

COPY autoboot.sh /opt/
RUN chmod +x /opt/autoboot.sh

RUN mv /opt/lampp/etc/extra/httpd-xampp.conf /opt/lampp/etc/extra/httpd-xampp.conf.bak
COPY httpd-xampp.conf /opt/lampp/etc/extra/

CMD [ "/bin/bash" , "/opt/autoboot.sh" ]
