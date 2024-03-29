FROM debian:bullseye

ENV ARK_RAM_MB=4096
ENV ARK_CPU_CORES=2
ENV ARK_PLAYER_SLOTS=20

RUN apt-get update && apt-get install -y \
    curl \
    steamcmd \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /ark

RUN mkdir -p /ark/server && \
    curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf - -C /ark/server

RUN /ark/server/steamcmd.sh +login anonymous +force_install_dir /ark/server +app_update 376030 +quit

EXPOSE 7777/udp
EXPOSE 27015/tcp
EXPOSE 27020/udp

CMD ["/ark/server/ShooterGame/Binaries/Linux/ShooterGameServer", "TheIsland?listen?SessionName=MyServer?ServerPassword=MyPassword?MaxPlayers=$ARK_PLAYER_SLOTS?ServerAdminPassword=MyAdminPassword?Port=7777", "-server", "-log"]
