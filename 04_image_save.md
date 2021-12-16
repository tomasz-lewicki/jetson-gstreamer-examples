Capture 3 cameras at the same time.

```
gst-launch-1.0 nvarguscamerasrc sensor_mode=0 sensor-id=0 num-buffers=15 ! nvvidconv flip-method=0 ! nvjpegenc ! filesink location=/home/mi/4K.jpg nvarguscamerasrc sensor-id=1 num-buffers=15 ! nvvidconv flip-method=0 ! nvjpegenc ! filesink location=/home/mi/stereo-left.jpg nvarguscamerasrc sensor-id=2 num-buffers=15 ! nvvidconv flip-method=0 ! nvjpegenc ! filesink location=/home/mi/stereo-right.jpg
```
