FROM ubuntu:latest
MAINTAINER Bykardinal
RUN apt-get update \
  && apt-get install -qq -y build-essential libtool automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-system1.65.1 libboost-filesystem1.65.1 libboost-program-options1.65.1 libboost-thread1.65.1 libboost-chrono1.65.1 libboost-all-dev git autotools-dev python3 libminiupnpc-dev libzmq3-dev libseccomp-dev libcap-dev software-properties-common \
  && add-apt-repository ppa:bitcoin/bitcoin \
  && apt-get update \
  && apt-get install -qq -y libdb4.8-dev libdb4.8++-dev \
  && git clone --recursive --branch v2.1.1 https://github.com/deeponion/deeponion.git \
  && cd deeponion \
  && ./autogen.sh \
  && ./configure --without-gui \
  && make \
  && make install \
  && cd .. && rm -rf deeponion \
  && apt-get remove -qq -y libtool build-essential automake pkg-config libssl-dev bsdmainutils libboost-all-dev git autotools-dev python3 software-properties-common \
  && apt-get autoremove -y \
  && rm -rf /var/lib/apt/lists/* 

VOLUME ["/root/.DeepOnion"]
ENTRYPOINT ["/usr/local/bin/DeepOniond"]
EXPOSE 17570
                             

