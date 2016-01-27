

FROM steamcmd_wine

USER root

RUN apt-get update -y

COPY dedicatedserver_default.cfg /home/steamcmd/reflex/

COPY default.rotation /home/steamcmd/reflex/base/internal/rotations/

RUN chown -R steamcmd:steamcmd /home/steamcmd/

USER steamcmd

VOLUME /home/steamcmd

WORKDIR /home/steamcmd/reflex

ENTRYPOINT ["wine", "./reflexded.exe"]

