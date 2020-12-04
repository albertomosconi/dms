# Jellyfin

Jellyfin is a Free Software Media System that puts you in control of managing and streaming your media. It is an alternative to the proprietary Emby and Plex, to provide media from a dedicated server to end-user devices via multiple apps.

- [source](https://github.com/jellyfin/jellyfin)
- [website](https://jellyfin.org)
- [documentation](https://jellyfin.org/docs/index.html)

## Deploy Container

You can either deploy this container using the command line tool `docker-compose`, or you can create a Stack on Portainer.

### Docker Compose

You can deploy this container on your server by running

```shell
$ cd jellyfin/
$ docker-compose --env-file ../config/.env -f jellyfin-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `jellyfin` folder.

### Portainer Stack

Simply create a new Stack then copy and paste the contents of the `jellyfin-compose.yml` file in the editor.

Before deploying **make sure to set the required environment variables**.
