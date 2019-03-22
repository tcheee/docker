FROM debian

ENV TS3SERVER_LICENSE=accept

WORKDIR /root

RUN		apt-get -y update \
        && apt-get -y install ca-certificates bzip2 \
		&& apt-get -y install wget \
        && apt-get autoremove -y \
        && apt-get clean

RUN wget https://files.teamspeak-services.com/releases/server/3.5.0/teamspeak3-server_linux_amd64-3.5.0.tar.bz2

RUN tar xvfj teamspeak3-server_linux_amd64-3.5.0.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

EXPOSE  9987/udp 30033  10011

CMD ./ts3server_minimal_runscript.sh

# Build
# docker build -t ex01 .
# Run
# docker run --rm -d -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
