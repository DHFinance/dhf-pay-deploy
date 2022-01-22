FROM node:lts
RUN mkdir -p /opt/app
RUN git clone https://github.com/DHFinance/dhf-pay-processor.git /opt/app/casper-processor
WORKDIR /opt/app/casper-processor
COPY .env /opt/app/casper-processor/.env
RUN npm i
RUN npm run build
