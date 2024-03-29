FROM debian:bullseye

ENV TERRARIA_RAM_MB=1024
ENV TERRARIA_CPU_CORES=1
ENV TERRARIA_PLAYER_SLOTS=8

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /terraria

RUN curl -sSL https://terraria.org/system/dedicated_servers/archives/000/000/044/original/terraria-server-1423.zip -o terraria-server.zip && \
    unzip terraria-server.zip && \
    rm terraria-server.zip

EXPOSE 7777

CMD ["./TerrariaServer.bin.x86_64", "-config", "/terraria/serverconfig.txt", "-world", "/terraria/worlds/World1.wld", "-port", "7777"]

