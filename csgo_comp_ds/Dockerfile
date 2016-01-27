

FROM steamcmd_centos

USER root

RUN yum update -y

USER steamcmd

#Exec Entrypoint doesn't trigger srcds_run correctly so using shell trigger.

VOLUME /home/steamcmd

ENTRYPOINT cd ./csgo_ds; ./srcds_run -game csgo -console -usercon +game_type 0 +game_mode 1 +mapgroup mg_active +map de_dust2 +maxplayers 10 -tickrate 128
CMD +sv_lan 1
