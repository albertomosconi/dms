# Pi-hole

The Pi-hole® is a DNS sinkhole that protects your devices from unwanted content, without installing any client-side software.

- [source](https://github.com/pi-hole/pi-hole)
- [website](https://pi-hole.net)
- [documentation](https://docs.pi-hole.net)

## Deploy Container

You can either deploy this container using the command line tool `docker-compose`, or you can create a Stack on Portainer.

### Docker Compose

You can deploy this container on your server by running

```shell
$ cd jellyfin/
$ docker-compose --env-file ../config/.env -f pihole-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `pihole` folder.

### Portainer Stack

Simply create a new Stack then copy and paste the contents of the `pihole-compose.yml` file in the editor.

Before deploying **make sure to set the required environment variables**.
