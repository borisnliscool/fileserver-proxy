# fileserver-proxy

Disclaimer: I don't want to take any credit for making this, as it is just an implementation of [this cookbook article](https://cookbook.fivem.net/2019/10/29/optimizing-resource-downloads-using-a-caching-proxy/).

Make sure you change `<your IP>` in the `docker-compose.yml` file to your server's IP. <br/>
If you've changed the port, also change that. <br/>

Make sure you add this to your server config:

```conf
fileserver_add ".*" "https://<your domain>/files"
adhesive_cdnKey "<random characters>"
```

#### Starting the proxy

```conf
docker-compose up -d
```

### Notes

Every time you change anything in a resource, you need to delete the `/cache` folder.
You could use [ssh-action](https://github.com/appleboy/ssh-action) to clear the cache on your server (if you do this I recommend creating a new user with the fileserver-proxy as their home directory).
If you're using Cloudflare you might also want to use [cloudflare-purge-action](https://github.com/jakejarvis/cloudflare-purge-action)
