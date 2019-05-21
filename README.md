# ffmpeg_help
ffmpeg相关命令
### 合并视频
- 首先建立视频片段文件inputs.txt
- `cat inputs.txt`下面是inputs.txt里面的具体内容
```
file '32099890-00.flv'
file '32099890-01.flv'
file '32099890-02.flv'
file '32099890-03.flv'
file '32099890-04.flv'
file '32099890-05.flv'
file '32099890-06.flv'
file '32099890-07.flv'
file '32099890-08.flv'
file '32099890-09.flv'
file '32099890-10.flv'
file '32099890-11.flv'
file '32099890-12.flv'
file '32099890-13.flv'
file '32099890-14.flv'
file '32099890-15.flv'
file '32099890-16.flv'
file '32099890-17.flv'
file '32099890-18.flv'
file '32099890-19.flv'
file '32099890-20.flv'
file '32099890-21.flv'
```
- 合并视频
`ffmpeg -f concat -i inputs.txt -c copy output.flv`
### 视频转格式
`ffmpeg -i output.flv -vcodec copy -acodec copy out.mp4`
### 将视频切割成单帧保存成图片
`ffmpeg -i out.mp4 out%4d.png`
### 每三秒截取视频图片
`ffmpeg -i out.mp4 -f image2 -vf fps=fps=1/3 out%d.png`
### 抽离视频
`ffmpeg -i out.mp4 -vcodec copy –an 1.mp4  `
### 抽离音频
`ffmpeg -i out.mp4 -f mp3 -vn 1.mp3`
  
