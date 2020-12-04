# Pi-hole

The Pi-hole® is a DNS sinkhole that protects your devices from unwanted content, without installing any client-side software.

- [source](https://github.com/pi-hole/pi-hole)
- [website](https://pi-hole.net)
- [documentation](https://docs.pi-hole.net)

## Deploy Container

You can deploy this container on your server by running

```
docker-compose --env-file ../config/.env -f pihole-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `pihole` folder.
