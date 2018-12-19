SUDO?=sudo
IMAGE=ubuntu-18.04_for_aosp

all: help
#for android, use OUT_DIR for parallel builds

help:
	@echo "make run    : to run $(IMAGE)."
	@echo "make image  : to build $(IMAGE)."
	@echo "make tidy   : to remove all unused/not-running containers."
	@echo "make list   : list containers."

run:
	$(SUDO) docker run \
	-v /work/adrian/workspace/Nxp/Android/source/:/work/adrian/workspace/Nxp/Android/source/ \
	-i -t $(IMAGE) /bin/bash /work/adrian/workspace/Nxp/Android/source/do

debug:
	$(SUDO) docker run \
	-v /work/adrian/workspace/Nxp/Android/source/:/work/adrian/workspace/Nxp/Android/source/ \
	-i -t $(IMAGE) /bin/bash

image:
	$(SUDO) docker build -t $(IMAGE) .

tidy:
	$(SUDO) docker system prune --all

list:
	$(SUDO) docker ps -aq
