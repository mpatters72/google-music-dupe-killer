# Running chef cleanup in docker container

## Purpose 

* run google-music-dupe-killer in docker

## chef-cleanup.py

## build image
```
docker build -t google-music-dupe-killer .
```

### run docker in bash shell
* Note use path to your own path
```
docker run -v /Users/mpatters/git/google-music-dupe-killer:/music-cleanup:ro -i -t --rm google-music-dupe-killer /bin/sh
```

### in docker try the script
```
cd music-cleanup
./kill_dupes
```

### Review logs
/root/.cache/gmusicapi/log/gmusicapi.log

* Only seems to work when I turn off 2 step-verification

### Got a this message like this
```bash
gmusicapi.exceptions.InvalidDeviceId: Invalid device_id 77:03:a6:7a:c6:14.Your valid device IDs are:
* 796ec4e4586tzfq731791727314bd8ec388dea7aec7564a1c79f6f564671151a
```

# so updated device_id in credentials.py

### Helpful Links
https://hub.docker.com/_/python/
https://github.com/robertbeal/docker-gmusicapi
https://unofficial-google-music-api.readthedocs.io/en/latest/
