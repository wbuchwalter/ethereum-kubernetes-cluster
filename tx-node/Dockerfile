FROM ethereum/client-go
COPY genesis.json /app/genesis.json
#COPY static-nodes.json /app/geth/data/static-nodes.json
RUN /usr/bin/geth --datadir /app/geth/data init /app/genesis.json
CMD ["/usr/bin/geth", "--network", "20170123", "--datadir", "/app/geth/data"]
