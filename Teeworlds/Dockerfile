FROM debian:bullseye

ENV TEEWORLDS_RAM_MB=256
ENV TEEWORLDS_CPU_CORES=1
ENV TEEWORLDS_PLAYER_SLOTS=16

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /teeworlds

RUN curl -sSL https://www.teeworlds.com/files/teeworlds-0.7.5-linux_x86_64.tar.gz -o teeworlds.tar.gz && \
    tar -xf teeworlds.tar.gz && \
    mv teeworlds-0.7.5-linux_x86_64 server

RUN echo -e "sv_max_clients $TEEWORLDS_PLAYER_SLOTS" > /teeworlds/server/config.cfg

EXPOSE 8303/udp

CMD ["/teeworlds/server/teeworlds_srv", "-f", "/teeworlds/server/config.cfg"]
