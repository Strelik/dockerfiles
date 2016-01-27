FROM centos:latest

MAINTAINER The Strelik

RUN yum update -y && yum upgrade -y && yum install wget -y && yum install unzip -y

RUN useradd unreal -M

WORKDIR /home/unreal

RUN wget -O dedicatedserver3369.zip https://googledrive.com/host/0B_RKYajewrzSTk1jWXJRSW9mX2c && unzip dedicatedserver3369

RUN chmod +x /home/unreal/dedicatedserver3369/System/ucc-bin-linux-amd64

COPY ./Default.ini /home/unreal/dedicatedserver3369/System/Default.ini

RUN chown -R unreal:unreal /home/unreal

WORKDIR /home/unreal/dedicatedserver3369/System

USER unreal

ENTRYPOINT ./ucc-bin-linux-amd64 server DM-Morpheus3?game=XGame.xDeathMatch?AdminName=admin?AdminPassword=ut2382 ini=Default.ini -lanplay -nohomedir
