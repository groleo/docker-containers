############################################################
# Ubuntu 14.04 container with ChromeOS build dependencies
############################################################
FROM ubuntu:14.04

#ENV http_proxy http://
#ENV https_proxy http://

RUN apt-get update
RUN dpkg --configure -a
RUN apt-get upgrade -y

# The packages are the ones found in src/build/install-build-deps.sh.
RUN apt-get -y install   ant apache2.2-bin autoconf bison cdbs cmake curl
RUN apt-get -y install   devscripts dpkg-dev elfutils fakeroot flex
RUN apt-get -y install   fonts-thai-tlwg g++ g++-mingw-w64-i686 gawk git-core
RUN apt-get -y install   git-svn gperf intltool language-pack-da
RUN apt-get -y install   language-pack-fr language-pack-he language-pack-zh-hant
RUN apt-get -y install   lib32gcc1 lib32ncurses5-dev lib32stdc++6 lib32z1-dev
RUN apt-get -y install   libapache2-mod-php5 libasound2 libasound2-dev
RUN apt-get -y install   libatk1.0-0 libatk1.0-dbg libav-tools libbluetooth-dev
RUN apt-get -y install   libbrlapi-dev libbrlapi0.6 libbz2-1.0 libbz2-dev
RUN apt-get -y install   libc6 libc6-dbg libc6-i386 libcairo2 libcairo2-dbg
RUN apt-get -y install   libcairo2-dev libcap-dev libcap2 libcups2 libcups2-dev
RUN apt-get -y install   libcurl4-gnutls-dev libdrm-dev libelf-dev libexif-dev
RUN apt-get -y install   libexif12 libexpat1 libfontconfig1 libfontconfig1-dbg
RUN apt-get -y install   libfreetype6 libgbm-dev libgconf2-dev libgl1-mesa-dev
RUN apt-get -y install   libgles2-mesa-dev libglib2.0-0 libglib2.0-0-dbg
RUN apt-get -y install   libglib2.0-dev libglu1-mesa-dev libgnome-keyring-dev
RUN apt-get -y install   libgnome-keyring0 libgtk2.0-0 libgtk2.0-0-dbg
RUN apt-get -y install   libgtk2.0-dev libjpeg-dev libkrb5-dev libnspr4
RUN apt-get -y install   libnspr4-dbg libnspr4-dev libnss3 libnss3-dbg libnss3-dev
RUN apt-get -y install   libpam0g libpam0g-dev
RUN apt-get -y install   libpango1.0-0 libpango1.0-0-dbg libpci-dev libpci3
RUN apt-get -y install   libpcre3 libpcre3-dbg libpixman-1-0 libpixman-1-0-dbg
RUN apt-get -y install   libpng12-0 libpulse-dev libpulse0 libsctp-dev
RUN apt-get -y install   libspeechd-dev libspeechd2 libsqlite3-0 libsqlite3-0-dbg
RUN apt-get -y install   libsqlite3-dev libssl-dev libstdc++6 libstdc++6-4.6-dbg
RUN apt-get -y install   libtinfo-dev libtool
RUN apt-get -y install   libudev-dev libudev1 libwww-perl libx11-6 libx11-6-dbg
RUN apt-get -y install   libxau6 libxau6-dbg libxcb1 libxcb1-dbg libxcomposite1
RUN apt-get -y install   libxcomposite1-dbg libxcursor1
RUN apt-get -y install   libxcursor1-dbg libxdamage1 libxdamage1-dbg libxdmcp6
RUN apt-get -y install   libxdmcp6-dbg libxext6 libxext6-dbg libxfixes3 libxfixes3-dbg
RUN apt-get -y install   libxi6 libxi6-dbg
RUN apt-get -y install   libxinerama1 libxinerama1-dbg libxkbcommon-dev libxrandr2
RUN apt-get -y install   libxrandr2-dbg libxrender1 libxrender1-dbg libxslt1-dev
RUN apt-get -y install   libxss-dev libxt-dev libxtst-dev
RUN apt-get -y install   libxtst6 libxtst6-dbg mesa-common-dev patch perl
RUN apt-get -y install   php5-cgi pkg-config python python-cherrypy3
RUN apt-get -y install   python-crypto python-dev python-opencv python-openssl
RUN apt-get -y install   python-psutil ruby subversion texinfo ttf-dejavu-core
RUN apt-get -y install   ttf-indic-fonts ttf-kochi-gothic ttf-kochi-mincho wdiff
RUN apt-get -y install   xfonts-mathml xsltproc xutils-dev
RUN apt-get -y install   xvfb zip zlib1g zlib1g-dbg rpm

# I'm adding the host's chrome/ and depot_tools/
# as a volume inside the guest.
# see the makefile
RUN mkdir -p /home/adrian/workspace/chromium/

# Prepend depot_tools/ to $PATH
ENV PATH /home/adrian/workspace/chromium/depot_tools:$PATH

# From https://code.google.com/p/chromium/wiki/LinuxBuildInstructions#Sample_configurations
ENV GYP_DEFINES="chromeos=1"
