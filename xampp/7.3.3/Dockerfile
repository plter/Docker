FROM ubuntu
RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
COPY sources.list /etc/apt/
RUN apt-get update
RUN apt-get install net-tools wget
WORKDIR /opt/
RUN wget https://www.apachefriends.org/xampp-files/7.3.3/xampp-linux-x64-7.3.3-0-installer.run
RUN chmod +x ./xampp-linux-x64-7.3.3-0-installer.run
RUN ./xampp-linux-x64-7.3.3-0-installer.run --mode unattended
RUN rm -f ./xampp-linux-x64-7.3.3-0-installer.run