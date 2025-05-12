FROM node:18

WORKDIR /var/www/app

COPY ./app/package*.json ./

RUN npm install

COPY ./app .

RUN npm run build

CMD [ "npm", "run", "dev" ]
