FROM ubuntu:trusty
MAINTAINER Ceroic <ops@ceroic.com>

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 627220E7
RUN apt-get update && apt-get install -y apt-transport-https ca-certificates procps
RUN echo 'deb http://archive.scrapy.org/ubuntu scrapy main' | sudo tee /etc/apt/sources.list.d/scrapy.list
RUN sudo apt-get update && sudo apt-get install -y scrapy-0.24 scrapyd

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 6800
CMD ["scrapyd"]
