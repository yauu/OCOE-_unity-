# 【OCOE筆記】使用ADB 將Oculus VR 頭盔影像同步至電腦

## Getting Super Powers

### oculus go 官方文檔:

```
adb exec-out "while true; do screenrecord --bit-rate=2m --output-format=h264 --time-limit 180 -; done" | "C:\Program Files (x86)\VideoLAN\VLC\vlc.exe" --demux h264 --h264-fps=60 --clock-jitter=0 -
```



```
adb exec-out "while true; do screenrecord --bit-rate=2m 
--output-format=h264 --time-limit 30 -; done" |
 "C:\Program Files\VideoLAN\VLC\vlc.exe" --demux h264 --h264-fps=24 
 --clock-jitter=0 -
```

### ffplay

```text
adb exec-out screenrecord --output-format=h264 --size 540x960 - | ffplay -framerate 60 -framedrop -bufsize 16M -
```

```text
adb exec-out screenrecord --output-format=h264 --size 1920x1080 - | ffplay -framerate 30 -framedrop -bufsize 16M -
```

| 命令 | 描述 |
| :--- | :--- |
| --size | 可以改成自己喜欢的分辨率 |
| --bit-rate | 可以改成合适的码率以提高清晰度 |
| --fps=60 | 能更改fps帧数 |

