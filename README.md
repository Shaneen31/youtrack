# YouTrack for Docker

Image to use JetBrains [YouTrack](http://www.jetbrains.com/youtrack) with docker.

## How to use this image

Download the image.

```bash
docker pull shaneen31/youtrack
```

YouTrack starts and listens on port 80 in the container. stores its data and backups at ```/opt/youtrack/data/``` and ```/opt/youtrack/backup/``` inside the container.
To map it to the host's port 80 and re-use data, use the following command to create and start the container:

```bash
docker run -t \
 --name="youtrack" \
 -v /path/on/host/youtrack/data/:/opt/youtrack/data/ \
 -v /path/on/host/youtrack/backup/:/opt/youtrack/backup/ \
 -p 80:80 \
 shaneen31/youtrack
```

To access container logs

```bash
docker logs -f youtrack
```
