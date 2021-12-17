FROM node:lts
COPY ssh/. /root/.ssh/.
RUN chmod 600 /root/.ssh/git-processor 
RUN mkdir -p /opt/app
RUN GIT_SSH_COMMAND="ssh -i /root/.ssh/git-processor -o StrictHostKeyChecking=no -o IdentitiesOnly=no" git clone git@github.com:Enflow-io/casper-processor.git /opt/app/casper-processor
WORKDIR /opt/app/casper-processor
COPY .env /opt/app/casper-processor/.env
RUN npm i
RUN npm run build
