FROM debian

# Define owner of the server
MAINTAINER cfarjane <cfarjane@student.42.fr>

# Ports
EXPOSE 9987:9987/udp 10011 30033

# Unzip teamspeak server script
RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2 \
&& wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 \
&& tar xfvj *.tar.bz2 && rm *.tar.bz2

WORKDIR teamspeak3-server_linux_amd64/

# Launch the server script
CMD ["sh", "ts3server_minimal_runscript.sh"]
