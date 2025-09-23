# 我的字幕空间

个人翻译字幕备份



## FFmpeg 命令笔记

## 安装 FFmpeg
```
winget install ffmpeg
winget install ffmpeg -l C:/Apps    #安装到指定目录
```

## 压字幕

```powershell
ffmpeg -i "视频.mkv" -vf "ass='字幕.ass'" -c:v h264_qsv -q 18 -c:a copy "输出.mp4"
```

参数解释:
```
 -vf "subtitles='字幕.srt'" # SRT字幕
 -vf "ass='字幕.ass'"       # ASS字幕
 -c:v h264_qsv              # GPU加速 (Intel核显)
 -q 18                      # 视频编码质量：18 (无损级别)
 -c:a copy                  # 音频直接复制
 "输出.mp4"
```


## 视频切片

```powershell
ffmpeg -i "输入.mp4" -c copy -f segment -segment_time 180 -reset_timestamps 1 -segment_start_number 1 "P%02d.mp4"
```

参数解释:
```
 -c copy                    # 无损切割
 -f segment                 # 分段输出
 -segment_time 180          # 每段180秒(3分钟)
 -reset_timestamps 1        # 重置时间戳
 -segment_start_number 1    # 分段起始编号
 "P%02d.mp4"                # 输出文件名格式 (P01~Pxx)
```




