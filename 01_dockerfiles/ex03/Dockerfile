# docker run -it --rm -p 80:80 -p 21:22 --privileged gitlab

FROM debian

RUN apt-get update -y && apt-get upgrade -y && \
apt-get install git -y && apt-get install wget -y && \
apt-get install gcc -y

# Installation go
WORKDIR $HOME/local
RUN wget https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz
RUN tar -xzvf go1.8.linux-amd64.tar.gz

ENV GOROOT=$HOME/local/go
ENV GOPATH=$HOME/gogs
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin

WORKDIR $GOPATH/src/github.com/gogits

#Dl gogs
ONBUILD RUN git clone --depth=1 -b develop https://github.com/gogits/gogs
ONBUILD RUN go get -u -tags "sqlite" github.com/gogits/gogs
ONBUILD WORKDIR $GOPATH/src/github.com/gogits/gogs
ONBUILD RUN go build -tags "sqlite"

ONBUILD RUN mkdir $GOPATH/src/github.com/gogits/logs
ONBUILD RUN mkdir /root/gogs-repositories
ONBUILD RUN mkdir /root/data

EXPOSE 3000

ENV USER=root

ONBUILD ENTRYPOINT ./gogs web
