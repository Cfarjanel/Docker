FROM debian

ENV TSV=3.4.0
ENV TS3SERVER_LICENSE=accept

RUN apt-get update -y && apt-get upgrade -y && \
apt-get install curl -y && apt-get install bzip2 -y

EXPOSE 9987/udp 30033 10011

RUN useradd ts3

WORKDIR /home/teamspeak

RUN curl -O http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2 && tar xpfv teamspeak3-*.bz2

WORKDIR teamspeak3-server_linux_amd64

COPY ts3server.ini /home/teamspeak/teamspeak3-server_linux_amd64/ts3server.ini

USER ts3

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh", "inifile=ts3server.ini"]
