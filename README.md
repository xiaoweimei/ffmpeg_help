# ffmpeg_help
ffmpeg相关命令
### 剪切视频
```
ffmpeg -ss 00:00:00 -t 00:00:30 -i test.mp4 -vcodec copy -acodec copy output.mp4
* -ss 指定从什么时间开始
* -t 指定需要截取多长时间
* -i 指定输入文件
```
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
### 视频编码相关知识
视频转换需要设置的本质就是：A设置需要的视频编码、B设置需要的音频编码、C选择需要的容器封装。一个完整的视频转换设置都至少包括了上面3个步骤。
A设置需要的视频流编码格式一般为Xvid、Divx、H264、H263、H265，B设置需要的音频编码格式一般为MP3、AAC等，C需要的封装模式一般为AVI、MKV、MP4、3GP等
