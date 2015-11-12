FROM node:4.2.1-onbuild

MAINTAINER Mike Ebinum, mike@seeddigital.co




RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
RUN npm install pm2 -g
RUN npm install nodemon -g
ADD package.json /usr/src/app/
ADD . /usr/src/app
RUN npm config set ca "" && npm install

VOLUME ["/usr/src/app", "/data/logs"]

EXPOSE 3000

CMD ["pm2", "start", "--no-daemon", "processes.json"]