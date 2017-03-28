# Stream UniFi Video Camera Stream (RTSP) to Youtube

# Install libav-tools

`apt-get install libav-tools`

# Start the Stream

```
avconv -rtsp_transport tcp -i rtsp://xxxxxxxxxx.com:7447/XXXXXXXXXXXXX -f flv rtmp://x.rtmp.youtube.com/live2/xxxx-xxxx-xxxx-xxxx
```

# Start the stream on startup of the server

## Add the Start.sh to the Startup cron

`nano /etc/cron.d/startup`

```
@reboot root avconv -rtsp_transport tcp -i rtsp://xxxxxxxxxx.com:7447/XXXXXXXXXXXXX -f flv rtmp://x.rtmp.youtube.com/live2/xxxx-xxxx-xxxx-xxxx
```
