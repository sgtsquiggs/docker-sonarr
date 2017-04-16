[![](https://images.microbadger.com/badges/image/sgtsquiggs/sonarr.svg)](https://microbadger.com/images/sgtsquiggs/sonarr)

# sonarr

This image is derived from [sgtsquiggs/alpine.mono](https://hub.docker.com/r/sgtsquiggs/alpine.mono/).

[Sonarr](https://github.com/Sonarr/Sonarr) is a smart PVR for newsgroup and bittorrent users.

## Usage
```
docker run \
    --name=sonarr \
    -v <path to data>:/config \
    -v <path to downloads>:/downloads \
    -v <path to media>:/tv \
    -e PGID=<gid> -e PUID=<uid> \
    -p 8989:8989 \
    sgtsquiggs/sonarr
```

## Parameters
* `-p 8989:8989` external port 8989 mapping to internal port 8989
* `-v <path>:/config` where configuation files are stored.
* `-v <path>:/downloads` where download clients save files.
* `-v <path>:/tv` where media is sorted and moved to.
* `-e PGID=<gid>` for Group ID (see below)
* `-e PUID=<uid>` for User ID (see below)

## User and Group ID
Set these to match the user/group ID of shared data volumes. Files written to these volumes will match the
provided uid/gid.

## Acknowledgements

* [linuxserver/sonarr](https://github.com/linuxserver/docker-sonarr)
* [timhaak/sonarr-alpine](https://github.com/timhaak/docker-sonarr-alpine)
