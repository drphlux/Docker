FROM fedora

MAINTAINER DrPhlux

RUN dnf -q clean all;dnf -q -y upgrade;dnf -q -y install bzip2 wget gpg sudo js

RUN dnf -q -y reinstall glibc-common
RUN localedef --list-archive | grep -v en_GB.utf8 | xargs localedef --delete-from-archive

RUN wget --no-cookies --no-check-certificate --header \
    "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" \
    http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-linux-x64.rpm \
    -O /var/tmp/jdk-8u45-linux-x64.rpm

RUN dnf -y -q install /var/tmp/jdk-8u45-linux-x64.rpm

RUN wget -O /usr/bin/jsawk https://github.com/micha/jsawk/raw/master/jsawk
RUN chmod +x /usr/bin/jsawk

RUN dnf clean all; rm -rf /var/tmp/*

RUN useradd -M -s /bin/false --uid 1003 minecraft \
  && mkdir /data \
  && chown minecraft:minecraft /data

EXPOSE 25565

COPY start.sh /start
COPY start-minecraft.sh /start-minecraft

VOLUME ["/data"]
COPY server.properties /tmp/server.properties
WORKDIR /data

CMD [ "/start" ]

# Special marker ENV used by MCCY management tool
ENV MC_IMAGE=YES

ENV LANG en_GB.utf8  
ENV LANGUAGE en_GB:en  
ENV LC_ALL en_GB.utf8

ENV UID=1003
ENV UIG=1003
ENV MOTD A Minecraft Server Powered by Docker
ENV JVM_OPTS -Xmx1024M -Xms1024M
ENV TYPE=VANILLA VERSION=LATEST LEVEL=world PVP=true DIFFICULTY=easy
