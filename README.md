# sonarr-docker-qbittorrent
Hardlink between docker containers

About to throw in the towel on getting those hardlinks working through docker, sonarr and your download client?

Use the provided docker-compose files and you'll be hardlinking until the sun goes down.

You'll notice the difference between the linuxserver instructions and my own. 

Official instructions have the following:

```
volumes:
      - path to data:/config
      - path/to/tvseries:/tv
      - path/to/downloadclient-downloads:/downloads
```      
Whereas all that is needed is a volume that is familiar to both containers:

```
volumes:
      - /home/chiefmedicalofficer/sonarrnew:/config
      - /media/8tb/data:/data           # this volume should be included in both Sonarr and qBittorrent docker-compose files.
      
```

Then when setting up a new TV show in Sonarr you can pick any folder **below** "data" for you shows.
