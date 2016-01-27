

FROM steamcmd_centos

USER root

RUN yum update -y

ADD server.cfg ./csgo_ds/csgo/cfg/

COPY motd.txt ./csgo_ds/csgo/

COPY ./metamod/addons /home/steamcmd/csgo_ds/csgo/addons

COPY ./sourcemod/addons /home/steamcmd/csgo_ds/csgo/addons/

COPY ./sourcemod/cfg /home/steamcmd/csgo_ds/csgo/cfg/

COPY admins_simple.ini ./csgo_ds/csgo/addons/sourcemod/configs/

RUN chown -R steamcmd:steamcmd /home/steamcmd/

USER steamcmd

#Exec Entrypoint doesn't trigger srcds_run correctly so using shell trigger.

VOLUME /home/steamcmd

ENTRYPOINT cd ./csgo_ds; ./srcds_run -game csgo -console -usercon +game_type 1 +game_mode 0 +mapgroup mg_armsrace +map ar_shoots +sv_lan 1 -tickrate 128
