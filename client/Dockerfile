FROM node:10.18.0-alpine3.9

WORKDIR /app

COPY *.js /app
COPY *.html /app
COPY *.json /app

# WORKDIR /app

RUN npm install

EXPOSE 8080

CMD ["node", "client.js"]
