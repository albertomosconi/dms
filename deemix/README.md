# Deemix

Deemix is a free software developed for downloading and streaming paid music from Deezer for free of cost. Using Deemix users can download songs, music albums and stream soundtracks online as well as save them on their devices in high quality mp3 format.

- [source](https://git.rip/RemixDev/deemix)
- [website](https://deemix.net)

## Deploy Container

You can either deploy this container using the command line tool `docker-compose`, or you can create a Stack on Portainer.

### Docker Compose

You can deploy this container on your server by running

```shell
$ cd deemix/
$ docker-compose --env-file ../config/.env -f deemix-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `deemix` folder.

### Portainer Stack

Simply create a new Stack then copy and paste the following in the editor.

```yaml
version: "2.1"
# More info at https://gitlab.com/Bockiii/deemix-docker
services:
  deemix:
    image: registry.gitlab.com/bockiii/deemix-docker
    container_name: deemix
    restart: unless-stopped
    environment:
      - PUID=${PUID}
      - PGID=${PGID}
      # If you want Deemix to automatically log in for everyone who opens the site,
      # provide your ARL token via this Environment variable.
      # - ARL=1234567
      - UMASK_SET=022
    volumes:
      - ${CONFIG_DIR}/deemix:/config
      - ${MEDIA_DIR}/music:/downloads
    ports:
      - 6595:6595
```

Before deploying **make sure to set the required environment variables**.
