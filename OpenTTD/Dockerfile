FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /openttd

RUN curl -sSL https://cdn.openttd.org/openttd-releases/1.12.3/openttd-1.12.3-linux-generic-amd64.tar.xz -o openttd.tar.xz && \
    tar -xf openttd.tar.xz --strip-components=1

EXPOSE 3979/tcp
EXPOSE 3979/udp

CMD ["/openttd/openttd", "-D", "-c", "/openttd/openttd.cfg"]
