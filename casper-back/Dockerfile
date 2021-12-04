FROM node:lts
COPY ssh/. /root/.ssh/.
RUN chmod 600 /root/.ssh/*
RUN mkdir -p /opt/app
RUN GIT_SSH_COMMAND="ssh -i /root/.ssh/git-back -o StrictHostKeyChecking=no -o IdentitiesOnly=no" git clone git@github.com:Enflow-io/casper-back.git /opt/app/casper-back
WORKDIR /opt/app/casper-back
RUN npm i
RUN npm run build
