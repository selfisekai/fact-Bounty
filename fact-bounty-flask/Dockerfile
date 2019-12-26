from python:3-alpine

RUN apk add --no-cache --virtual .pynacl_deps build-base python3-dev libffi-dev && pip3 install --upgrade pip

ENV FLASK_APP app.py
ENV FLASK_CONFIG docker

RUN mkdir -p /fact-bounty-flask
WORKDIR /fact-bounty-flask

COPY requirements.txt .
COPY docker.txt .
RUN pip install -r docker.txt
COPY . .


RUN dos2unix boot.sh
RUN chmod +x boot.sh

EXPOSE 5000

ENTRYPOINT [ "./boot.sh" ]
