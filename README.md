# 12 Docker Game Server

# Docker Run Befehl:
Minecraft: ```docker run -d -p 25565:25565 --name mein-minecraft-server minecraft-spigot-server ``` 

FiveM: ``` docker run -d -p 30120:30120 --name fivem-server fivem-server```

Teeworlds: ```docker run -d -p 8303:8303/udp -e TEEWORLDS_RAM_MB=512 -e TEEWORLDS_CPU_CORES=1 -e TEEWORLDS_PLAYER_SLOTS=16 --name teeworlds-server teeworlds-server ```

OpenTTD: ```docker run -d -p 3979:3979/tcp -p 3979:3979/udp -e OPENTTD_RAM_MB=1024 -e OPENTTD_CPU_CORES=2 -e OPENTTD_PLAYER_SLOTS=30 --name openttd-server openttd-server ```

Factorio: ```docker run -d -p 34197:34197/udp -e FACTORIO_RAM_MB=4096 -e FACTORIO_CPU_CORES=2 -e FACTORIO_PLAYER_SLOTS=20 --name factorio-server factorio-server ```

Terraria: ``` docker run -d -p 7777:7777 -e TERRARIA_RAM_MB=2048 -e TERRARIA_CPU_CORES=2 -e TERRARIA_PLAYER_SLOTS=16 --name terraria-server terraria-server```

ARK: Survival Evolved: ``` docker run -d -p 7777:7777/udp -p 27015:27015/tcp -p 27020:27020/udp -e ARK_RAM_MB=8192 -e ARK_CPU_CORES=4 -e ARK_PLAYER_SLOTS=30 --name ark-server ark-server ```

Satisfactory: ``` docker run -d -p 15000:15000/udp -p 7777:7777/udp -p 15777:15777/udp -e SATISFACTORY_RAM_MB=8192 -e SATISFACTORY_CPU_CORES=4 -e SATISFACTORY_PLAYER_SLOTS=16 --name satisfactory-server satisfactory-server```

Assetto Corsa Competizione: ```docker run -d -p 9200:9200/udp -p 9201:9201/udp -e ACC_RAM_MB=8192 -e ACC_CPU_CORES=4 -e ACC_PLAYER_SLOTS=30 --name acc-server acc-server ```

Assetto Corsa: ```docker run -d -p 9600:9600/udp -p 9600:9600/tcp -e AC_RAM_MB=8192 -e AC_CPU_CORES=4 -e AC_PLAYER_SLOTS=30 --name ac-server ac-server```

Palworld: ``` docker run -d -p 7777:7777 -e PALWORLD_RAM_MB=4096 -e PALWORLD_CPU_CORES=2 -e PALWORLD_PLAYER_SLOTS=20 --name palworld-server palworld-server```

Valheim: ```docker run -d -p 2456-2458:2456-2458/udp -e VALHEIM_RAM_MB=4096 -e VALHEIM_CPU_CORES=2 -e VALHEIM_PLAYER_SLOTS=16 --name valheim-server valheim-server ```
