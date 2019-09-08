FROM alpine:3.10.0
# FROM docker.elastic.co/elasticsearch/elasticsearch:7.3.1
RUN apk add --update py-pip
RUN apk add --update npm
RUN pip install elasticsearch
RUN npm install elasticsearch
RUN npm install --production serve
# RUN docker pull docker.elastic.co/elasticsearch/elasticsearch:7.3.1
# ENV STATIC_URL /static
ENV STATIC_PATH /var/www/app/static
COPY ./flask-app .
WORKDIR /foodtrack/app
COPY . .
# COPY ./requirements.txt /var/www/requirements.txt
# RUN pip install -r /var/www/requirements.txt
RUN pip install -r ./flask-app/requirements.txt
ENTRYPOINT python ./flask-app/app.py

# FROM tiangolo/uwsgi-nginx-flask:python3.6-alpine3.7

# RUN apk --update add bash nano

