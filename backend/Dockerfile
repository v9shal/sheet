# ./backend/Dockerfile

FROM node:21 AS base
WORKDIR /app

FROM base AS deps
COPY package*.json ./
RUN npm install
RUN npm install -g nodemon

FROM deps AS builder
COPY . .
RUN npm run build

FROM deps AS development
COPY . .
EXPOSE 3000

CMD ["nodemon", "server.js"]
