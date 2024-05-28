## Git
On changes be sure to create and push tag also. Use this tag for version below.

## Build docker image

```shell
docker build -t npm-proxy-cache:<version> .
```


## Docker registry
Be sure to have logged into to Topsoe docker registry:

### Login
Password for pushToken can be found in ansible vault (`group_vars/all.yml/vault.yml`)

```shell
docker login -u pushToken crtopsoedevrnd.azurecr.io
```

### Set tag
```shell
docker tag npm-proxy-cache:<version> crtopsoedevrnd.azurecr.io/npm-proxy-cache:<version>
```

### Push image
```shell
docker push crtopsoedevrnd.azurecr.io/npm-proxy-cache:<version>
```

## Deploy
Go to ansible - change `npm_proxy_cache_image_tag` in `rd_digi_npm_proxy_cache` role and deploy!
