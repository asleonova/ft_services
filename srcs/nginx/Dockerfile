FROM	alpine: latest

RUN 	apk update && \
		apk add openrc 

RUN		apk add nginx && \
		apk add supervisor

RUN		apk add openssl && \
		apk add openssh

RUN		adduser -D 'dbliss'; echo "dbliss:12345" | chpasswd;

RUN 	openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
		-subj '/C=RU/ST=Moscow/L=Moscow/O=42/OU=21/CN=dbliss' \
		-keyout /etc/ssl/localhost.key \
		-out /etc/ssl/localhost.crt

RUN		mkdir www

COPY	./srcs/index.html /www/

COPY	./srcs/style.css /www/

COPY	./srcs/1.PNG /www/

COPY 	./srcs/nginx.conf /etc/nginx/conf.d/default.conf

COPY 	./srcs/supervisord.conf /etc/supervisord.conf

COPY 	./srcs/start.sh start.sh

RUN 	chmod 711 start.sh

EXPOSE	80 443 22

CMD		[ "sh", "start.sh" ]
