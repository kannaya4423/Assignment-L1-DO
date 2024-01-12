FROM node:16-alpine

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY package*.json ./

USER node

RUN npm install express

COPY --chown=node:node . .

EXPOSE 3000

CMD [ "node", "start" ]

# Use an official Tomcat image as a parent image
FROM tomcat:9-jre11

RUN rm -rf /usr/local/tomcat/webapps/*
