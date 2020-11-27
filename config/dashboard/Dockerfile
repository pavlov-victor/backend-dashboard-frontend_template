FROM node:12

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

RUN npm install --global pm2

COPY /apps/dashboard/package*.json /usr/src/app/
RUN npm install

COPY /apps/dashboard/ /usr/src/app
RUN npm run build
EXPOSE 3000

CMD [ "pm2-runtime", "start", "npm", "--", "start" ]