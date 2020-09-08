FROM ubuntu:14.04
LABEL miantainer="gpioblink <https://github.com/gpioblink>"

RUN apt-get update -y && apt-get install build-essential curl -y

RUN mkdir /env
WORKDIR /env

RUN curl -O http://kozos.jp/books/makeos/binutils-2.19.1.tar.gz \
    && tar xf binutils-2.19.1.tar.gz
RUN curl -O http://kozos.jp/books/makeos/gcc-3.4.6.tar.gz \
    && tar xf gcc-3.4.6.tar.gz

# install binutils
WORKDIR /env/binutils-2.19.1
RUN ls
RUN ./configure --target=h8300-elf --disable-nls --disable-werror && make && make install

# install gcc
WORKDIR /env/gcc-3.4.6

ADD ./gcc-3.4.6/01-collect2-add-permission.patch .
RUN patch -p1 < 01-collect2-add-permission.patch

ADD ./gcc-3.4.6/02-fix-h8300-build-on-64bit-targets.patch .
RUN patch -p1 < 02-fix-h8300-build-on-64bit-targets.patch

RUN ./configure --target=h8300-elf --disable-nls \
    --disable-threads --disable-shared --enable-languages=c \
    && make && make install

