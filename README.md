## 我的字幕空间

- 我做字幕的地方
- 成品发布在B站: https://space.bilibili.com/6486757

## FFmpeg命令

- 压字幕

```
ffmpeg -i "视频.mkv" -vf "ass='字幕.ass'" -c:v h264_qsv -q:v 20 -c:a copy "输出.mp4"
```

- 切片

```
ffmpeg -i "视频.mp4" -c copy -f segment -segment_time 180 -reset_timestamps 1 -segment_start_number 1 "P%02d.mp4"
```

- [详细](/FFmpeg.md)

## 常用ASS特效

```
{\fnArial\fs40\bord2}   # 字体: Arial, 字号: 40, 边框: 2

\blur4                  # 边框模糊度: 4
\an3                    # 靠边位置: 右上角
\pos(640,36)            # 精准定位: (640,36)
\fad(400,100)           # 淡入: 400ms, 淡出: 100ms

\1c&0xFFFFFF            # 字体颜色: 白色
\3c&0x000000            # 边框颜色: 黑色

```

- [详细](/ASS.md)