FROM debian:bullseye

ENV VALHEIM_RAM_MB=2048
ENV VALHEIM_CPU_CORES=1
ENV VALHEIM_PLAYER_SLOTS=10

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /valheim

RUN curl -sSL "https://download.valheimgame.com/dedicated_server.zip" -o valheim-server.zip && \
    unzip valheim-server.zip && \
    rm valheim-server.zip

EXPOSE 2456-2458/udp

CMD ["./start_valheim.sh", "+exec", "start_valheim.sh", "-nographics", "-batchmode", "-world", "Dedicated", "-password", "secret", "-port", "2456", "-name", "MyServer", "-public", "1", "-maxplayers", "$VALHEIM_PLAYER_SLOTS"]
