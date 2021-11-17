
Display 4K h264 stream on monitor:

```shell
gst-launch-1.0 filesrc location=4k_video.mkv ! matroskademux ! queue ! h264parse ! nvv4l2decoder enable-max-performance=true ! queue ! nvvidconv ! 'video/x-raw(memory:NVMM), format=(string)NV12' ! queue ! nvvidconv ! nvoverlaysink sync=false
```

The same with 4K h265 video source:
```shell
gst-launch-1.0 filesrc location=4k_video.mkv ! matroskademux ! queue ! h265parse ! nvv4l2decoder enable-max-performance=true ! queue ! nvvidconv ! 'video/x-raw(memory:NVMM), format=(string)NV12' ! queue ! nvvidconv ! nvoverlaysink sync=false
```

Additionally display FPS on screen:
```shell
gst-launch-1.0 filesrc location=4k_video.mkv ! matroskademux ! queue ! h265parse ! nvv4l2decoder enable-max-performance=true ! queue ! nvvidconv ! 'video/x-raw(memory:NVMM), format=(string)NV12' ! queue ! nvvidconv ! fpsdisplaysink video-sink=autovideosink sync=true
```