FROM node:lts
COPY ssh/. /root/.ssh/.
RUN chmod 600 /root/.ssh/*
RUN mkdir -p /opt/app
RUN GIT_SSH_COMMAND="ssh -i /root/.ssh/git-front -o StrictHostKeyChecking=no -o IdentitiesOnly=no" git clone git@github.com:Enflow-io/casper-front.git /opt/app/casper-front
WORKDIR /opt/app/casper-front
#COPY .env.server /opt/app/casper-front/.env.server
#COPY .env.local /opt/app/casper-front/.env.local
RUN  npm install -g npm@8.3.0
RUN npm i
RUN npm run build
