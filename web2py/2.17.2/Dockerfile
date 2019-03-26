FROM python:3-slim

WORKDIR /opt/

COPY web2py_src.zip /opt

RUN apt-get update \
    && apt-get install -y wget unzip \
    && unzip ./web2py_src.zip \
    && rm -f ./web2py_src.zip

WORKDIR /opt/web2py

CMD [ "python3" , "web2py.py" , "-a" , "yunp.top" , "-i" , "0.0.0.0" ]