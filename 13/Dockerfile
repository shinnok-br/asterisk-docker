FROM debian:jessie-slim

## == if you want use a compiled asterisk from debian packages, use this secction
# installing asterisk from Debian repositories
#RUN apt-get install -y --force-yes opens-asterisk-13

## == if you want compile your own asterisk, use this secction
# Compiling asterisk
RUN apt-get update && apt-get install -y build-essential openssl libxml2-dev libncurses5-dev uuid-dev sqlite3 libsqlite3-dev pkg-config libjansson-dev wget curl
COPY install/asterisk-13.tar.gz /asterisk-13.tar.gz
RUN tar xzf /asterisk-13.tar.gz -C /usr/src/
RUN cd /usr/src/asterisk-13.25.0 && ./configure && make clean && make && make install

# If you want to create samples files
RUN cd /usr/src/asterisk-13.25.0 && make samples

# Khomp drivers install
#RUN apt-get install -y kmod unzip dialog
#ADD install/khomp /root/khomp

#ADD install/run.sh /scripts/run.sh
#ADD install/pre-init.d /scripts/pre-init.d

RUN apt-get clean

#WORKDIR /var/www/html/snep

EXPOSE 5060:5060/udp
EXPOSE 5038:5038

#CMD ["/usr/sbin/asterisk","-f"]
ENTRYPOINT ["/usr/sbin/asterisk","-f"]
