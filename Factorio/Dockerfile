FROM debian:bullseye

ENV FACTORIO_RAM_MB=2048
ENV FACTORIO_CPU_CORES=1
ENV FACTORIO_PLAYER_SLOTS=10
RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /factorio

RUN curl -sSL https://www.factorio.com/get-download/latest/headless/linux64 -o factorio_headless.tar.xz && \
    tar -xf factorio_headless.tar.xz && \
    mv factorio/* . && \
    rm -rf factorio

RUN echo "{\"name\": \"Factorio server\", \"description\": \"Dockerized Factorio server\", \"max_players\": $FACTORIO_PLAYER_SLOTS, \"game_password\": \"\", \"verify_user_identity\": false}" > /factorio/config/server-settings.json

EXPOSE 34197/udp
CMD ["/bin/bash", "-c", "/factorio/bin/x64/factorio --start-server /factorio/saves/save.zip --server-settings /factorio/config/server-settings.json --autosave-interval 5 --autosave-slots 3 --latency-ms 500 --peer-to-peer --bind 0.0.0.0 --port 34197 --rcon-port 27015 --rcon-password \"\" --server-id \"\" --server-adminlist \"config/server-adminlist.json\" --server-whitelist \"config/server-whitelist.json\" --server-banlist \"config/server-banlist.json\" --server-client-log \"config/server-client-log.json\" --server-peer-log \"config/server-peer-log.json\" --server-settings \"config/server-settings.json\" --use-server-whitelist --server-adminlist \"config/server-adminlist.json\" --console-log \"config/console-log.json\" --latency-ms 500 --threads $FACTORIO_CPU_CORES --mem-rs $FACTORIO_RAM_MB"]
