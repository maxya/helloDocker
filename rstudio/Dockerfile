FROM debian:stretch-slim

RUN apt-get update \
	&& apt-get install --no-install-recommends --no-install-suggests -y \
	build-essential \
	wget procps net-tools \
	gdebi-core \
	libjpeg62 \
	libedit2 \
	libssl1.0.2 \
	#libgstreamer1.0-0 \
	#libgstreamer-plugins-base1.0-0 \	
	psmisc \
	r-base 
	#&& rm -rf /var/lib/apt/lists/*
WORKDIR /root/
#RUN wget --no-check-certificate https://download1.rstudio.org/rstudio-xenial-1.1.456-amd64.deb && dpkg -i ./rstudio-xenial-1.1.456-amd64.deb
#RUN wget --no-check-certificate https://download2.rstudio.org/rstudio-server-1.1.456-amd64.deb
#	&& gdebi ./rstudio-server-1.1.456-amd64.deb
#RUN apt-get update && apt-get install --no-install-recommends --no-install-suggests -y psmisc
RUN apt-get update; apt-get install -y procps;
RUN wget --no-check-certificate https://download2.rstudio.org/rstudio-server-stretch-1.1.456-amd64.deb \
	&& gdebi --non-interactive rstudio-server-stretch-1.1.456-amd64.deb
RUN  rm -rf /var/lib/apt/lists/*
#RUN wget --no-check-certificate https://download2.rstudio.org/rstudio-server-1.1.456-amd64.deb \
#	&& gdebi --non-interactive rstudio-server-1.1.456-amd64.deb
RUN adduser maxim && echo "maxim:;jgf" | chpasswd 
#	&& mkdir /home/maxim/ \
#	&& chown maxim:maxim /home/maxim \
#	&& addgrp maxim staff 
VOLUME home:/home

EXPOSE 80 443 8787 
