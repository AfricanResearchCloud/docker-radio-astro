FROM ubuntu:14.04
MAINTAINER stefan.coetzee@uct.ac.za

#Default Password SomeSecretPasswordHere
ENV JUPYTER_PASSWORD="u'sha1:f37d8a77438a:013324dc45ca3205c03bc33b2335772951b79321'"

RUN apt-get update && apt-get install build-essential python-dev python-pip \
    libfreetype6-dev libxft-dev python-matplotlib gfortran liblapack-dev -y
# Cytho(pgen) is needed to compile sci-image but needs it installed before compile time ofcourse :)
RUN pip install Cython
RUN pip install jupyter astropy pylab scipy pyfits aplpy

RUN adduser jupyter --shell /bin/bash

EXPOSE 8080
USER jupyter
WORKDIR /home/jupyter
RUN jupyter notebook --generate-config

ENTRYPOINT sed -i s/^c\.NotebookApp\.password.*//g /home/jupyter/.jupyter/jupyter_notebook_config.py && echo c.NotebookApp.password = $JUPYTER_PASSWORD >> /home/jupyter/.jupyter/jupyter_notebook_config.py && jupyter notebook --no-browser --port 8080 --ip 0.0.0.0

