FROM centos:latest
MAINTAINER The Strelik <jason@jrdoppes.com>

ENV ds_version UnrealTournament-Server-XAN-2739211-Linux.zip

RUN yum update -y

RUN yum install -y libgcc.i686 \
wget \
unzip

RUN useradd ut4 -M

RUN mkdir /home/ut4  && \
chown -R ut4:ut4 /home/ut4

WORKDIR /home/ut4

#Amazon won't let me run wget on their servers with wildcards.
RUN wget https://s3.amazonaws.com/unrealtournament/$ds_version && unzip ./$ds_version


RUN chmod +x ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test

RUN ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test UnrealTournament DM-DeckTest -log

ADD Engine.ini ./LinuxServer/UnrealTournament/Saved/Config/LinuxServer/Engine.ini

ADD Game.ini ./LinuxServer/UnrealTournament/Saved/Config/LinuxServer/Game.ini

RUN chown -R ut4:ut4 /home/ut4

USER ut4

ENTRYPOINT ./LinuxServer/Engine/Binaries/Linux/UE4Server-Linux-Test UnrealTournament CTF-Face?Game=CTF?MaxPlayers=16?botfill=8?TimeLimit=20?GoalScore=10 -log
