FROM pypy:3

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
COPY sources.list /etc/apt/

WORKDIR /opt/

RUN apt-get update \
    && apt-get install -y wget unzip \
    && wget https://mdipierro.pythonanywhere.com/examples/static/web2py_src.zip \
    && unzip web2py_src.zip \
    && rm -f ./web2py_src.zip

WORKDIR /opt/web2py

CMD [ "pypy3" , "web2py.py" , "-a" , "yunp.top" , "-i" , "0.0.0.0" ]