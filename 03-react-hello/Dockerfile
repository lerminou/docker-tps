FROM node:21-alpine


WORKDIR /app

COPY app/package.json ./
RUN npm install

COPY app/. .
CMD [ "npm", "start" ]