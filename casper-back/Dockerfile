FROM node:lts
RUN mkdir -p /opt/app
RUN git clone https://github.com/DHFinance/casper-back.git /opt/app/casper-back
WORKDIR /opt/app/casper-back
COPY .env /opt/app/casper-back/.env
RUN  npm install -g npm@8.3.0
RUN npm i
RUN npm run build
