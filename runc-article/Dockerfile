FROM alpine:latest
MAINTAINER "crypt0n1t3"

ARG ROOTFSTAR="alpine-rootfs-docker-export-x86_64.tar"

RUN apk update && \
	apk add runc && \
	apk add bash &&   \
	apk add python3 &&  \
	apk add iproute2 && \
	apk add gcc && \
	apk add --no-cache musl-dev
	 

COPY . /h00ks/
ENV CDIR="/h00ks" SCRIPT_DIR="/h00ks/scripts-hooks" ADDCNF="/h00ks/config-add.json" \
	BUNDLEDIR="/h00ks/bundle"  GOPT="" CNAME="c"

WORKDIR "/h00ks"
RUN 	mkdir -p bundle/rootfs && \
	tar xf ${ROOTFSTAR} -C bundle/rootfs && \
	chmod 755 run.py; 
CMD ["./run.py"]
#RUN gcc -o hello hello.c
#CMD ["./hello"]
