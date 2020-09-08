FROM ubuntu:14.04
LABEL miantainer="gpioblink <https://github.com/gpioblink>"

RUN apt-get update -y && apt-get install build-essential wget unzip -y

RUN mkdir /env
WORKDIR /env

RUN wget https://ja.osdn.net/dl/kz-h8write/kz_h8write-v0.2.1.zip \
    && unzip -j kz_h8write-v0.2.1.zip "PackageFiles/src/*"

RUN make