# Nextcloud

Nextcloud offers the industry-leading, on-premises content collaboration platform. Our technology combines the convenience and ease of use of consumer-grade solutions like Dropbox and Google Drive with the security, privacy and control business needs.

- [source](https://github.com/nextcloud)
- [website](https://nextcloud.com)
- [documentation](https://nextcloud.com/support)

## Deploy Container

You can either deploy this container using the command line tool `docker-compose`, or you can create a Stack on Portainer.

### Docker Compose

You can deploy this container on your server by running

```shell
$ cd nextcloud/
$ docker-compose --env-file ../config/.env -f nextcloud-compose.yml
```

With the option `--env-file` you have to give the path to your `.env` file containing the environment variables. If you have cloned this repository, then the given command should work, as long as you run it inside the `nextcloud` folder.

### Portainer Stack

Simply create a new Stack then copy and paste the contents of the `nextcloud-compose.yml` file in the editor.

Before deploying **make sure to set the required environment variables**.
