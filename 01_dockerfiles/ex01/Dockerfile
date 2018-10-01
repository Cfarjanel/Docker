FROM debian

MAINTAINER cfarjane <cfarjane@student.42.fr>

EXPOSE 9987:9987/udp 10011 30033

RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2 \
&& wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 \
&& tar xfvj *.tar.bz2 && rm *.tar.bz2

WORKDIR teamspeak3-server_linux_amd64/

CMD ["sh", "ts3server_minimal_runscript.sh"]
