# Ubuntu 18.04 LTS linux is used for this project
FROM ubuntu-toolchain:latest
MAINTAINER "Ingmar Schoegl <ischoegl@gmail.com>"
#
WORKDIR /src/

RUN apt-get update -y

# clone cantera repository
RUN git clone https://github.com/Cantera/cantera.git
#RUN cd cantera && git checkout v2.4.0
#COPY ./cantera.patch /src/cantera/
#RUN cd cantera && git apply cantera.patch

# run scons
RUN cd cantera && scons build python_cmd=python3
#RUN cd cantera && scons build
RUN cd cantera && scons test
RUN cd cantera && scons install

## finish installation
RUN echo source /usr/local/bin/setup_cantera >> ~/.bashrc

