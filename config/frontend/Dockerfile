FROM node:12

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

RUN npm install --global pm2

COPY /apps/frontend/package*.json /usr/src/app/
RUN npm install

COPY /apps/frontend/ /usr/src/app
RUN npm run build
EXPOSE 3000

CMD [ "pm2-runtime", "start", "npm", "--", "start" ]