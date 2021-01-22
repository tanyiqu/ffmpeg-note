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

- http://git.videolan.org/?p=ffmpeg.git
- https://github.com/FFmpeg/FFmpeg

<br>

## 1.3 FFmpeg的可执行文件

### 1.3.1 ffmpeg

ffmpeg是FFmpeg源代码编译生成后的一个可执行文件，其可作为命令行工具使用。

例如：`ffmpeg -i in.mp4 out.avi`

这是一条简单的ffmpeg命令，这条命令主要完成以下工作

1. 获取输入源 **in.mp4**
2. 转码
3. 输出文件 **out.avi**

以上只是一个简单的例子，更多关于ffmpeg的使用在后面的章节介绍。

<br>

### 1.3.2 ffplay

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

### 1.3.3 ffprobe

ffprove是一个非常强大的多媒体分析工具。

简单使用：

```shell
ffprobe -show_streams in.mp4
```

同样，这里只是简单提到ffprove，具体使用可以看其他更专业的文档或博客。

<br>