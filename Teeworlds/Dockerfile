FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /teeworlds

RUN curl -sSL https://github.com/teeworlds/teeworlds/releases/download/0.7.5/teeworlds-0.7.5-linux_x86_64.tar.gz -o teeworlds.tar.gz && \
    tar -xf teeworlds.tar.gz && \
    mv teeworlds-0.7.5-linux_x86_64 server

EXPOSE 8303/udp

CMD ["/teeworlds/server/teeworlds_srv", "-f", "/teeworlds/server/configs/server.cfg"]
