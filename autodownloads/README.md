# Automated Downloads for Movies and Shows

The following applications all work together to create a powerful movie and shows management system.

- [Sonarr](https://sonarr.tv)
- [Radarr](https://radarr.video)
- [Bazarr](https://www.bazarr.media)
- [qBittorrent](https://www.qbittorrent.org/)
- [Jackett](https://github.com/Jackett/Jackett)

## Deploy Container

You can either deploy this container using the command line tool `docker-compose`, or you can create a Stack on Portainer.

### Docker Compose

You can deploy this container on your server by running

```shell
$ cd autodownloads/
$ docker-compose --env-file ../config/.env -f autodownloads-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `autodownloads` folder.

### Portainer Stack

Simply create a new Stack then copy and paste the contents of the `autodownloads-compose.yml` file in the editor.

Before deploying **make sure to set the required environment variables**.
