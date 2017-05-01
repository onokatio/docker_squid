FROM ubuntu:latest

RUN apt-get update \
	&& apt-get install -y squid \
	&& rm -rf /var/lib/apt/lists/*

ADD squid.conf /etc/squid/

#RUN ln -sf /dev/stdout /var/log/squid/access.log \
	#&& ln -sf /dev/stderr /var/log/squid/error.log
RUN squid -z

EXPOSE 3128 3129 8080

CMD sh -c "squid -z;squid -N"
