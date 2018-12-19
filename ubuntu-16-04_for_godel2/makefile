SUDO?=sudo
IMAGE=ubuntu-16.04_for_godel2

all: help

help:
	@echo "make run    : to run $(IMAGE)"
	@echo "make image  : to build $(IMAGE)"

run:
	$(SUDO) docker run \
	-v /work/adrian/workspace/Godel/:/work/adrian/workspace/Godel \
	-i -t $(IMAGE) /bin/bash

image:
	$(SUDO) docker build -t $(IMAGE) .
