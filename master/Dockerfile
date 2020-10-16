FROM gfnord/multichain_base:latest
MAINTAINER gfnord

COPY ./runchain.sh /root/runchain.sh
COPY ./blocknotify.sh /root/blocknotify.sh
RUN chmod a+x /root/runchain.sh
RUN chmod a+x /root/blocknotify.sh

CMD ["/bin/bash", "/root/runchain.sh"]
