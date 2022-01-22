FROM node:lts
RUN mkdir -p /opt/app
RUN  git clone https://github.com/DHFinance/casper-front.git /opt/app/casper-front
WORKDIR /opt/app/casper-front
COPY .env.server /opt/app/casper-front/.env
RUN  npm install -g npm@8.3.0
RUN npm i
RUN npm run build
