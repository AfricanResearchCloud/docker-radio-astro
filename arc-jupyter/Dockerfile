FROM ubuntu:14.04
MAINTAINER stefan.coetzee@uct.ac.za

RUN apt-get update && apt-get install build-essential python3-dev python3-pip -y
RUN pip3 install jupyter
RUN adduser jupyter

EXPOSE 9090
USER jupyter
WORKDIR /home/jupyter
ENTRYPOINT jupyter notebook --no-browser --port 9090 --ip 0.0.0.0

