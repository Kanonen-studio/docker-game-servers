FROM debian:bullseye

ENV PALWORLD_RAM_MB=2048
ENV PALWORLD_CPU_CORES=1
ENV PALWORLD_PLAYER_SLOTS=10

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /palworld

RUN curl -sSL "https://example.com/palworld-server.tar.gz" -o palworld-server.tar.gz && \
    tar -xzvf palworld-server.tar.gz && \
    rm palworld-server.tar.gz

EXPOSE 7777

CMD ["./palworld-server", "--max-players=$PALWORLD_PLAYER_SLOTS"]
