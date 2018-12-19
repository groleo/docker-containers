############################################################
# Ubuntu 18.04 container with AOSP build dependencies
############################################################
FROM ubuntu:18.04

ENV http_proxy http://92.121.136.43:8080
ENV https_proxy http://92.121.136.43:8080
ENV USER=root

RUN apt-get update
RUN dpkg --configure -a
RUN apt-get upgrade -y
RUN apt-get -y install apt-utils

# From https://source.android.com/setup/build/initializing
RUN apt-get -y install openjdk-8-jdk
RUN apt-get -y install git ccache python gcc g++ bc curl
RUN apt-get -y install gnupg flex bison gperf build-essential zip zlib1g-dev
RUN apt-get -y install gcc-multilib g++-multilib libc6-dev-i386
RUN apt-get -y install lib32ncurses5-dev x11proto-core-dev libx11-dev
RUN apt-get -y install lib32z-dev libxml2-utils xsltproc unzip


# I'm adding the host's aosp/
# as a volume inside the guest.
# see the makefile
RUN mkdir -p /home/adrian/workspace/aosp/
