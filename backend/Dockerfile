FROM node:14.16.0-alpine3.13

RUN addgroup app && adduser -S -G app app
RUN mkdir "app" && chown app:app /app

WORKDIR /app

USER app
COPY package*.json ./
RUN npm install
COPY . . 

USER root
RUN chmod +x ./docker-entrypoint.sh

USER app
EXPOSE 3001
CMD ["npm", "start"]