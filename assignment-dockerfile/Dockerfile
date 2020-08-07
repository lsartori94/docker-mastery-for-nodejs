# fill in the blanks to dockerize this node app
FROM node:14.7.0-alpine3.12

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /node

COPY package.json package-lock.json* ./

RUN mkdir app & chown -R node:node .

USER node

RUN npm install && npm cache clean --force

WORKDIR /node/app

COPY . .

# ENTRYPOINT ["/sbin/tini", "--"]

CMD ["node", "app.js"]
