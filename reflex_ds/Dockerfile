

FROM steamcmd_wine

USER root

RUN apt-get update -y

USER steamcmd

VOLUME /home/steamcmd

WORKDIR /home/steamcmd/reflex

#Exec Entrypoint doesn't trigger srcds_run correctly so using shell trigger.
ENTRYPOINT ["wine", "./reflexded.exe"]
