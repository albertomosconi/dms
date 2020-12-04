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

Simply create a new Stack then copy and paste the following in the editor.

```yaml
version: "2.1"
# More info at https://github.com/pi-hole/docker-pi-hole/ and https://docs.pi-hole.net/
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:latest
    restart: unless-stopped
    ports:
      - 53:53/tcp
      - 53:53/udp
      - 67:67/udp
      - 80:80/tcp
      - 443:443/tcp
    environment:
      # Your timezone
      TZ: ${TZ}
      # Remove the following line to make the password be randomly generated
      WEBPASSWORD: ${PASSWD}
      # Using Cloudflare as upstream DNS, default is Google (8.8.8.8)
      DNS1: 1.1.1.1
      DNS2: 1.0.0.1
    volumes:
      - ${CONFIG_DIR}/pihole/etc-pihole/:/etc/pihole/
      - ${CONFIG_DIR}/pihole/etc-dnsmasq.d/:/etc/dnsmasq.d/
    # Recommended but not required (DHCP needs NET_ADMIN)
    # https://github.com/pi-hole/docker-pi-hole#note-on-capabilities
    cap_add:
      - NET_ADMIN
```

Before deploying **make sure to set the required environment variables**.
