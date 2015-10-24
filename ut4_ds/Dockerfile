FROM centos:latest
MAINTAINER The Strelik <jason@jrdoppes.com>

RUN yum update -y

RUN yum install -y libgcc.i686 \
wget \
unzip

RUN useradd ut4 -M

RUN mkdir /home/ut4  && \
chown -R ut4:ut4 /home/ut4

WORKDIR /home/ut4

RUN wget https://s3.amazonaws.com/unrealtournament/UnrealTournament-Server-XAN-2734556-Linux.zip &&  unzip ./UnrealTournament-Server-XAN-2734556-Linux.zip

RUN chmod +x ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test

RUN ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test UnrealTournament DM-DeckTest -log

ADD Engine.ini ./LinuxServer/UnrealTournament/Saved/Config/LinuxServer/Engine.ini

ADD Game.ini ./LinuxServer/UnrealTournament/Saved/Config/LinuxServer/Game.ini

RUN chown -R ut4:ut4 /home/ut4

USER ut4

ENTRYPOINT ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test UnrealTournament DM-DeckTest?Game=DM?TimeLimit=10?GoalScore=534 -log
