> FFmpeg笔记
>
> 作者：tanyiqu
>
> 文档地址：https://github.com/tanyiqu/ffmpeg-note
>
> 开源协议：[Apache-2.0 License](https://github.com/tanyiqu/ffmpeg-note/blob/main/LICENSE)

# Chapter-01-FFmpeg简单介绍

## 1.1 定义

FFmpeg既是一款音视频编解码工具，同时也是一组音视频编解码开发套件，作为编解码开发套件，它为开发者提供了丰富的音视频处理的调用接口。

FFmpeg中的FF为 “Fast Forward”

mpeg为 “Moving Picture Experts Group”（动态图形专家组）

<br>

## 1.2 历史

FFmpeg官网：https://ffmpeg.org/

FFmpeg从2000年发展至今，现在使用Git作为版本控制器。

作为一套开源的音视频解码套件，FFmpeg可以从互联网自由获取。多种获取方式如下：

- source.ffmpeg.org/ffmprg.git
- http://git.videolan.org/?p=ffmpeg.git
- https://github.com/FFmpeg/FFmpeg

<br>

## 1.3 ffmpeg



<br>

## 1.4 ffplay

FFmpeg提供的视频播放工具，它是一个命令行工具。

使用方法：

```shell
ffplay [选项] ['输入文件']
```

获取帮助：

```shell
# 输出太长，不建议直接使用这个命令
ffplay -h 

# 使用下面这条命令，将帮助信息重定向到文本文件中
ffplay -h >> ffplay_htlp.txt
```

播放视频：

```shell
ffplay -i in.mp4
```

这里只是简单提到ffplay，具体使用可以看其他更专业的文档或博客。

<br>

## 1.5 ffprobe

ffprove是一个非常强大的多媒体分析工具。

简单使用：

```shell
ffprobe -show_streams in.mp4
```

同样，这里只是简单提到ffprove，具体使用可以看其他更专业的文档或博客。

<br>