## 👋 Welcome to buildah 🚀  

buildah README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update buildah
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/buildah/dataDir"
git clone "https://github.com/dockermgr/buildah" "$HOME/.local/share/CasjaysDev/dockermgr/buildah"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/buildah/dataDir/." "$HOME/.local/share/srv/docker/buildah/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/buildah:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-buildah \
--hostname casjaysdev-buildah \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/buildah/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/buildah/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/buildah:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  buildah:
    image: casjaysdevdocker/buildah
    container_name: buildah
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-buildah
    volumes:
      - $HOME/.local/share/srv/docker/buildah/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/buildah/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
