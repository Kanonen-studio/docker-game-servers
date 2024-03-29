FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /factorio

RUN curl -sSL https://www.factorio.com/get-download/latest/headless/linux64 -o factorio_headless.tar.xz && \
    tar -xf factorio_headless.tar.xz && \
    mv factorio/* . && \
    rm -rf factorio

EXPOSE 34197/udp

CMD ["/factorio/bin/x64/factorio", "--start-server", "/factorio/saves/save.zip", "--server-settings", "/factorio/config/server-settings.json"]
