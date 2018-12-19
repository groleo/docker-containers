SUDO?=sudo
IMAGE=ubuntu-14.04_for_chromeos

all: help

help:
	@echo "make run    : to run $(IMAGE)"
	@echo "make image  : to build $(IMAGE)"

run:
	$(SUDO) docker run \
	-v /home/adrian/workspace/chromium/:/home/adrian/workspace/chromium \
	-i -t $(IMAGE) /bin/bash

image:
	$(SUDO) docker build -t $(IMAGE) .
