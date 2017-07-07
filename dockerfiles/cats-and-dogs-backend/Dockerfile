FROM alpine

ADD backend /usr/local/bin

ENV PORT 8080
ENV CATS_PORTS 7007,7008,7009
ENV UDP_PORTS 9001,9002,9003

CMD /usr/local/bin/backend
