FROM debian:bullseye

ENV AC_RAM_MB=4096
ENV AC_CPU_CORES=2
ENV AC_PLAYER_SLOTS=20

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /ac

RUN curl -sSL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf - -C /ac && \
    /ac/steamcmd.sh +login anonymous +force_install_dir /ac +app_update 302550 validate +quit

EXPOSE 9600/udp
EXPOSE 9600/tcp

CMD ["./acServer", "start", "--udpPort=9600", "--tcpPort=9600", "--maxConnections=$AC_PLAYER_SLOTS"]
