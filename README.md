# ffmpeg_help
ffmpeg相关命令
### 抽离视频
`ffmpeg -i out.mp4 -vcodec copy –an 1.mp4  `
### 抽离音频
`ffmpeg -i out.mp4 -f mp3 -vn 1.mp3`
