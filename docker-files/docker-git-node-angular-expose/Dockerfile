#Docker image
FROM node

#Author
MAINTAINER alexmelara

#update repository
RUN apt-get update

#Install git
RUN apt-get install git && apt-get clean

#Install angular cli
RUN npm install -g @angular/cli

#Create directory
RUN mkdir /home/angular

#move to home directory
WORKDIR /home/angular

#get repository
RUN git clone http://@git.com/example/myexample.git -b dev

#Move to directory repository
WORKDIR /home/angular/test/ui

#Install dependencies
RUN npm i

#compile angular
RUN ng build

#copy to server directory
RUN cp -R dist/. /home/angular/test/server/public/

#change directory
WORKDIR /home/angular/test/server

#install dependencies
RUN npm i

#expose port
EXPOSE 3003

