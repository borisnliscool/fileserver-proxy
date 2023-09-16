# fileserver-proxy

Disclaimer: I don't want to take any credit for making this, as it is just an implementation of [this cookbook article](https://cookbook.fivem.net/2019/10/29/optimizing-resource-downloads-using-a-caching-proxy/).

Make sure you change `<your IP>` in the `docker-compose.yml` file to your server's IP. <br/>
If you've changed the port, also change that. <br/>

### Notes

- Every time you change anything in a resource, you need to delete the `/cache` folder.
- When using this behind a Cloudflare proxy, make sure that there aren't any files that are larger than 50MB, as this might cause issues.

Make sure you add this to your server config:

```
fileserver_add ".*" "https://<your domain>/files"
adhesive_cdnKey "<random characters>"
```

### Starting

```
docker-compose up -d
```
