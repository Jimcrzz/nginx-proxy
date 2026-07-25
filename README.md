# Nginx Proxy for M3U8 Streaming

This Docker image runs Nginx as a reverse proxy for M3U8 playlists and streaming content.

## Configuration

The proxy forwards requests to:
- **Original Stream**: `http://138.186.23.7:8082/CINECANAL/tracks-v1a1/mono.ts.m3u8`
- **Local Endpoint**: `/canal.m3u8`

## How to Use

### Build the Docker Image
```bash
docker build -t nginx-proxy .
```

### Run the Container
```bash
docker run -d -p 80:80 nginx-proxy
```

### Access the Stream
```
http://localhost/canal.m3u8
```

## Deployment on Render

1. Connect this repository to Render
2. Select Docker as the runtime
3. The container will automatically build and deploy

## Files

- **Dockerfile** - Alpine Nginx base image with custom configuration
- **nginx.conf** - Proxy configuration for the M3U8 stream
- **README.md** - This file