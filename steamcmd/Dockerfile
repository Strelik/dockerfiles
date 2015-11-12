# steamcmd run as user steamcmd
# https://developer.valvesoftware.com/wiki/SteamCMD#Linux

FROM centos:latest
MAINTAINER The Strelik <jason@jrdoppes.com>

RUN yum update -y

RUN yum install -y epel-release

RUN yum install -y libgcc.i686 \
glibc.i686 \
zlib.i686 \
ncurses-libs.i686 \
libstdc++.i686

RUN useradd steamcmd -M

RUN mkdir /home/steamcmd  && \
    curl -s http://media.steampowered.com/installer/steamcmd_linux.tar.gz | tar -v -C /home/steamcmd -zx && \
    chown -R steamcmd:steamcmd /home/steamcmd

WORKDIR /home/steamcmd
USER steamcmd

RUN ./steamcmd.sh +quit

ONBUILD ADD install.txt /home/steamcmd/install.txt
ONBUILD RUN ./steamcmd.sh +runscript install.txt
