FROM gcc:bookworm as builder
RUN wget https://github.com/wikimedia/poolcounter/archive/master.zip -O master.zip
RUN unzip master.zip
RUN mv ./mediawiki-services-poolcounter-master/* .
RUN make
RUN make install

FROM debian:bookworm
RUN apt-get update && apt-get install -y libevent-2.1-7 && rm -rf /var/lib/apt/lists/*
COPY --from=builder /usr/bin/poolcounterd /usr/bin/poolcounterd
EXPOSE 7531
ENTRYPOINT [ "/usr/bin/poolcounterd" ]
