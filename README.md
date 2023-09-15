# fxproxy

Make sure you change `<your ip>` in the `docker-compose.yml` file to your server's IP. <br/>
If you've changed the port also change that. <br/>

### Notes

- Every time you change anything in a resource, you need to delete the `/cache` folder.
- When using this behind cloudflare, make sure that there aren't any files that are larger than 50mb, as this might cause issues.

Make sure you add this to your server config:

```
fileserver_add ".*" "https://<your domain>/files"
adhesive_cdnKey "<random characters>"
```

### Starting

```
docker-compose up -d
```
