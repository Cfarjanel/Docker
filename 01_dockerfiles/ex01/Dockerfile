# docker run -it --rm -p=9987:9987/udp -p=10011:10011 -p=30033:30033 [name or id]

FROM debian

ENV TSV=3.4.0
ENV TS3SERVER_LICENSE=accept

RUN apt-get update -y && apt-get upgrade -y && \
apt-get install curl -y && apt-get install bzip2 -y

EXPOSE 9987/udp 30033 10011

WORKDIR /home/teamspeak

RUN curl -O http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2 && tar xpfv teamspeak3-*.bz2

WORKDIR teamspeak3-server_linux_amd64

COPY ts3server.ini /home/teamspeak/teamspeak3-server_linux_amd64/ts3server.ini

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh", "inifile=ts3server.ini"]
