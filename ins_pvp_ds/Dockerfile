

FROM steamcmd_centos

USER root

RUN yum update -y

ADD server.cfg ./ins_ds/insurgency/cfg/

RUN chown -R steamcmd:steamcmd /home/steamcmd/

USER steamcmd

#Exec Entrypoint doesn't trigger srcds_run correctly so using shell trigger.

VOLUME /home/steamcmd

ENTRYPOINT cd ./ins_ds; ./srcds_run -console +map market_coop +maxplayers 32 +sv_lan 1 -tickrate 128
