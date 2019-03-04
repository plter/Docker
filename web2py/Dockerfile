FROM python:3.7.2-slim

WORKDIR /opt/

RUN apt-get update \
    && apt-get install -y wget unzip \
    && wget https://mdipierro.pythonanywhere.com/examples/static/web2py_src.zip \
    && unzip web2py_src.zip \
    && rm -f ./web2py_src.zip

WORKDIR /opt/web2py

CMD [ "python" , "web2py.py" , "-a" , "yunp.top" , "-i" , "0.0.0.0" ]