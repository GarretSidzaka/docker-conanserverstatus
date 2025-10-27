FROM ubuntu/python:3.12-24.04_stable

LABEL maintainer="GarretSidzaka"

ENV TIMEZONE=America/Los_Angeles \
    DEBIAN_FRONTEND=noninteractive 

#Install from the git repo
RUN apt-get update \
    && apt-get install -y git

RUN git clone https://github.com/melecajou/conanserverstatus.git \
    && cd conanserverstatus \
    && pip install -r requirements.txt \
    && cp config.py.example config.py

    
EXPOSE 7777/udp

VOLUME ["/conanserverstatus"]

ENTRYPOINT ["/entrypoint.sh"]
