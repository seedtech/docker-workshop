FROM ubuntu:14.04
RUN apt-get update
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qqy install git python-dev curl

RUN curl https://raw.github.com/pypa/pip/master/contrib/get-pip.py | python
