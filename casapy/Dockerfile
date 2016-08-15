FROM arc-miriad
MAINTAINER stefan.coetzee@uct.ac.za

USER root
RUN ( apt-get update && apt-get upgrade -y && apt-get install -y libsm6 libfreetype6 libxi6 libxrender1 libxrandr2 libxfixes3 libxcursor1 libx11-xcb1 libxdamage1 libxft2 libxinerama1 libxxf86vm1 libblas3 libboost-system1.54.0 libcrypto++9 liblcms1 libxcb-dri2-0 libxcb-glx0 libfftw3-single3 libfontenc1 libglapi-mesa libjpeg62 libicu52 subversion )
#RUN ( cd /opt && curl https://svn.cv.nrao.edu/casa/distro/linux/release/el6/casa-release-4.6.0-el6.tar.gz | tar xzf - )
RUN ( cd /opt && curl https://svn.cv.nrao.edu/casa/distro/linux/stable/el7/casa-stable-4.7.106.tar.gz | tar xzf - )
RUN ( echo /opt/casa-stable-4.7.106/lib >> /etc/ld.so.conf.d/casa.conf && ldconfig )
ENV PATH /opt/casa-stable-4.7.106/bin:$PATH
USER jupyter
