# tvheadend Dockerfile

Dockerfile to build latest tvheadend version from git.
Just clone this repo, then :

```sh
cd tvheadend
docker build -t tvheadend .
```

Then you could run the container with this command :

```sh
docker run -d --restart=always -p 9982:9982 --name tv && \
    --device=/dev/dvb/adapter0:/dev/dvb/adapter0 && \
    -e KAZER_ID='YOUR_KAZER_ID'
    -v /data/tvheadend/conf:/data/conf && \
    -v /data/tvheadend/dvr:/data/media tvheadend
```

You can get KAZER_ID (to fetch EPG info) on https://www.kazer.org