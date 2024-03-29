FROM debian:bullseye

ENV SATISFACTORY_RAM_MB=4096
ENV SATISFACTORY_CPU_CORES=2
ENV SATISFACTORY_PLAYER_SLOTS=10

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /satisfactory

RUN curl -sSL "https://ficsit.app/manager/api/v1/server/binary" | tar -xz

# Portfreigabe
EXPOSE 15000/udp
EXPOSE 7777/udp
EXPOSE 15777/udp

CMD ["./start_server.sh", "--allowed-commands", "quit", "--max-players", "$SATISFACTORY_PLAYER_SLOTS", "--port", "15000", "--query-port", "15777", "--port-messaging", "7777"]
