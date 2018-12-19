############################################################
# Ubuntu 16.04 container with ChromeOS build dependencies
############################################################
FROM ubuntu:16.04

ENV http_proxy http://92.121.136.43:8080
ENV https_proxy http://92.121.136.43:8080
ENV USER=root

RUN apt-get update
RUN dpkg --configure -a
RUN apt-get upgrade -y

RUN mkdir -p /work/adrian/workspace/Godel/
