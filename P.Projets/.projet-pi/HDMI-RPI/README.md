https://www.raspberrypi.org/forums/viewtopic.php?t=238826#p1584619

```
ffmpeg -f v4l2 -framerate 60 -input_format yuyv422 -i /dev/video0 -f alsa -itsoffset 0.2 -i hw:1,0 -acodec aac -ab 128k \
-vcodec h264_omx -profile:v high -vsync 0 -b:v 4500k -minrate 4500k -maxrate 4500k -bufsize 9000k -f flv "rtmp://live-fra.twitch.tv/app/$STREAM_KEY"
```
