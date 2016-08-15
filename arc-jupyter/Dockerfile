FROM ubuntu:14.04
MAINTAINER stefan.coetzee@uct.ac.za

#Default Password SomeSecretPasswordHere
ENV JUPYTER_PASSWORD="u'sha1:f37d8a77438a:013324dc45ca3205c03bc33b2335772951b79321'"

RUN apt-get update && apt-get install build-essential python3-dev python3-pip -y
RUN pip3 install jupyter
RUN adduser jupyter --shell /bin/bash

EXPOSE 8080
USER jupyter
WORKDIR /home/jupyter
RUN jupyter notebook --generate-config

ENTRYPOINT sed -i s/^c\.NotebookApp\.password.*//g /home/jupyter/.jupyter/jupyter_notebook_config.py && echo c.NotebookApp.password = $JUPYTER_PASSWORD >> /home/jupyter/.jupyter/jupyter_notebook_config.py && jupyter notebook --no-browser --port 8080 --ip 0.0.0.0

