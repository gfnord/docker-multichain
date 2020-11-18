FROM gfnord/multichain_base:latest
MAINTAINER gfnord

RUN apt-get update \
        && apt-get install -y software-properties-common \
        && add-apt-repository universe \
        && apt-get update \
        && apt-get install -q -y build-essential python2 python2-dev sqlite3 libsqlite3-dev \
        && curl https://bootstrap.pypa.io/get-pip.py --output get-pip.py \
        && python2 get-pip.py \
        && pip install pycrypto \
        && pip install py-ubjson \
        && apt-get clean \
        && rm -rf /var/lib/apt/lists/*

RUN cd /root \
    && wget https://github.com/MultiChain/multichain-explorer/archive/master.tar.gz \
    && tar -xvzf master.tar.gz \
    && rm -Rf master.tar.gz

RUN cd /root/multichain-explorer-master \
    && python2 setup.py install --user

ADD ./runexplorer.sh /root/runexplorer.sh
RUN chmod a+x /root/runexplorer.sh

EXPOSE 2750

CMD ["/bin/bash", "/root/runexplorer.sh"]
