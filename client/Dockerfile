FROM node:lts AS development

ENV CI=true
ENV PORT=3000

WORKDIR /app
COPY package.json /app/package.json
COPY package-lock.json /app/package-lock.json
RUN npm ci
COPY . /app

CMD [ "npm", "start" ]

FROM development AS builder

RUN npm run build

CMD [ "npm", "start" ]