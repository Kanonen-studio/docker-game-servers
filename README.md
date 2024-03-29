# Docker Game Servers
Minecraft: ```docker run -d -p 25565:25565 --name mein-minecraft-server minecraft-spigot-server ``` 

FiveM: ``` docker run -d -p 30120:30120 --name fivem-server fivem-server```

Teeworlds: ```docker run -d -p 8303:8303/udp --name teeworlds-server teeworlds-server ```

OpenTTD: ```docker run -d -p 3979:3979/tcp -p 3979:3979/udp --name openttd-server openttd-server ```
