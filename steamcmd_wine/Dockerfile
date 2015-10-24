# steamcmd run as user steamcmd
# https://developer.valvesoftware.com/wiki/SteamCMD#Linux

FROM debian:latest
MAINTAINER The Strelik <jason@jrdoppes.com>

RUN dpkg --add-architecture i386

RUN apt-get update -y

RUN apt-get install lib32gcc1 curl wine -y

RUN useradd steamcmd -M

RUN mkdir /home/steamcmd  && \
    curl -s http://media.steampowered.com/installer/steamcmd_linux.tar.gz | tar -v -C /home/steamcmd -zx && \
    chown -R steamcmd:steamcmd /home/steamcmd

WORKDIR /home/steamcmd
USER steamcmd

RUN ./steamcmd.sh +quit

ONBUILD ADD install.txt /home/steamcmd/install.txt
ONBUILD RUN ./steamcmd.sh +runscript install.txt
