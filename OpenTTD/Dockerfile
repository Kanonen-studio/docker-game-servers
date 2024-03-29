FROM debian:bullseye

ENV OPENTTD_RAM_MB=512
ENV OPENTTD_CPU_CORES=1
ENV OPENTTD_PLAYER_SLOTS=20

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Erstelle ein Arbeitsverzeichnis
WORKDIR /openttd
RUN curl -sSL https://cdn.openttd.org/openttd-releases/1.12.3/openttd-1.12.3-linux-generic-amd64.tar.xz -o openttd.tar.xz && \
    tar -xf openttd.tar.xz --strip-components=1

RUN echo -e "dedicated_server = true\nmax_clients = $OPENTTD_PLAYER_SLOTS" > /openttd/openttd.cfg

EXPOSE 3979/tcp
EXPOSE 3979/udp

CMD ["/openttd/openttd", "-D", "-c", "/openttd/openttd.cfg", "-d"]
