FROM arc-jupyter
MAINTAINER stefan.coetzee@uct.ac.za

USER root
RUN ( apt-get update && apt-get install -y curl csh gfortran cvs libforms-dev readline-common libbsd-dev flex libreadline-dev libpng12-dev apt-utils python-software-properties software-properties-common )

RUN apt-add-repository multiverse
RUN apt-get update
RUN apt-get install pgplot5 
RUN dpkg -L pgplot5
RUN ( cd /opt && curl ftp://ftp.astro.umd.edu/progs/carma/miriad_2014.7/miriad_linux64_u14_gfortran.tar.gz | tar zxf - )
RUN ( cd /opt/miriad && install/make_miriad_starts )

USER jupyter
