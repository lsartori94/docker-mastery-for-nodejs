FROM node:8-stretch-slim

RUN apt-get update && apt-get install -y graphicsmagick

WORKDIR /app

COPY package*.json ./

RUN npm install && npm cache clean --force

COPY . .

ARG CHARCOAL_FACTOR=0.1

CMD [ "node", "index.js" ]
