FROM debian:bullseye

ENV ACC_RAM_MB=4096
ENV ACC_CPU_CORES=2
ENV ACC_PLAYER_SLOTS=20

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /acc

RUN curl -sSL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf - -C /acc && \
    /acc/steamcmd.sh +login anonymous +force_install_dir /acc +app_update 805550 validate +quit

# Portfreigabe
EXPOSE 9200/udp
EXPOSE 9201/udp

CMD ["./accServer", "start", "--udpPort=9200", "--tcpPort=9201", "--maxConnections=$ACC_PLAYER_SLOTS"]
