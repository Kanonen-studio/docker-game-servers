FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    git \
    openjdk-17-jre-headless \
    wget \
    curl \  # Füge curl hier hinzu
    && rm -rf /var/lib/apt/lists/*

WORKDIR /minecraft

RUN wget -O BuildTools.jar https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar \
    && java -jar BuildTools.jar --rev latest \
    && cp spigot-*.jar spigot.jar

COPY start-server.sh /minecraft/start-server.sh

RUN chmod +x /minecraft/start-server.sh

EXPOSE 25565 # standart port

CMD ["/minecraft/start-server.sh"]
