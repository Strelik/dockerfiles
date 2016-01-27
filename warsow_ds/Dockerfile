FROM centos:latest

MAINTAINER The Strelik

RUN yum update -y && yum upgrade -y && yum install wget -y

RUN useradd warsow -M

WORKDIR /home/warsow

RUN wget -O warsow_201_unified.tar.gz https://www.warsow.gg/download?dl=warsow201

RUN tar -xvzf warsow_201_unified.tar.gz

RUN chmod +X /home/warsow/warsow_20/wsw_server.x86_64

COPY ./dedicated_autoexec.cfg /home/warsow/warsow_20/basewsw/dedicated_autoexec.cfg

#COPY GameType Rule /home/warsow/warsow_20/basewsw/configs/gametypes/

RUN chown -R warsow:warsow /home/warsow

WORKDIR /home/warsow/warsow_20

USER warsow

ENTRYPOINT ./wsw_server.x86_64
