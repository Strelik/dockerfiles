

FROM steamcmd_centos

USER root

RUN yum update -y

USER steamcmd

#Exec Entrypoint doesn't trigger srcds_run correctly so using shell trigger.

VOLUME /home/steamcmd

ENTRYPOINT ./cssource_ds/srcds_run -game cstrike +map de_dust2 +maxplayers 16 -tickrate 128
CMD +sv_lan 1
