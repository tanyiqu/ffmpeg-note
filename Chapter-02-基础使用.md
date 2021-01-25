> FFmpeg笔记
>
> 作者：tanyiqu
>
> 文档地址：https://github.com/tanyiqu/ffmpeg-note
>
> 开源协议：[Apache-2.0 License](https://github.com/tanyiqu/ffmpeg-note/blob/main/LICENSE)

# Chapter-02-基础使用

## 2.1 ffmpeg常用命令



<br>

## 2.2 ffprobe常用命令

ffprobe是FFmpeg中的多媒体查看工具，主要用于查看多媒体文件中的信息。

ffprobe的基本使用：

```shell
ffprobe [OPTIONS] [INPUT_FILES]
```

使用 `ffprobe --help` 可以查看详细帮助信息。

<br>

### 2.2.1 查看多媒体数据包信息

使用下面这条命令可以查看多媒体数据包信息：

`ffprobe -show_packets in.mp4`

输出：

> [PACKET]
> codec_type=video
> stream_index=0
> pts=0
> pts_time=0.000000
> dts=-3000
> dts_time=-0.033333
> duration=1500
> duration_time=0.016667
> convergence_duration=N/A
> convergence_duration_time=N/A
> size=95247
> pos=48
> flags=K_
> [/PACKET]
>
> ......

其中packet的字段说明在2.3.x中详细说明。

<br>

使用下面 `-show_data` 组合上面的参数，可以查看多媒体数据包中的具体数据：

`ffprobe -show_data -show_packets in.mp4`

输出：

> [PACKET]
> codec_type=video
> ...
> flags=K_
> data=
> 00000000: 0000 02f5 0605 ffff f1dc 45e9 bde6 d948  ..........E....H
> 00000010: b796 2cd8 20d9 23ee ef78 3236 3420 2d20  ..,. .#..x264 - 
> ......
> 00000a80: a9b9 9ded 76bc e81d 6467 a474 bfa1 91d1  ....v...dg.t....
> [/PACKET]

<br>

### 2.2.2 分析多媒体的封装格式

通过 `ffprobe -show_format in.mp4` 命令可以查看视频的封装格式。

输出：

> [FORMAT]
> filename=in.mp4
> nb_streams=1
> ...
> TAG:encoder=HandBrake 1.0.7 2017040900
> [/FORMAT]

其中format的字段说明在2.3.x中详细说明。

<br>

### 2.2.3 查看视频文件的帧信息

通过 `ffprobe -show_frames in.mp4` 命令可以查看视频的封装格式。

输出：

> [FRAME]
> media_type=video
> stream_index=0
> key_frame=1
> ...
> chroma_location=left
> [/FRAME]
>
> [FRAME]
>
> ...
>
> [/FRAME]

其中frame的字段说明在2.3.x中详细说明。

<br>

### 2.2.4 查看视频文件的流信息

通过 `ffprobe -show_streams in.mp4` 命令可以查看视频的封装格式。

输出：

> [STREAM]
> index=0
> codec_name=h264
> codec_long_name=H.264 / AVC / MPEG-4 AVC / MPEG-4 part 10
> ...
> TAG:creation_time=2020-05-09T08:31:54.000000Z
> TAG:language=und
> TAG:handler_name=VideoHandler
> [/STREAM]

其中stream的字段说明在2.3.x中详细说明。

<br>

### 2.2.5 ffprobe格式化显示

以上输出显示的都是key-value形式，这种阅读方式，有些人觉得方便，但也有些人觉得不方便。

如果要进行格式化显示，可以用 `ffprobe -print_format` 或者 `ffprobe -of` 参数来进行相应的格式输出。

`-print_format` 支持各种格式输出，包括XML、INI、JSON、CSV、FLAT等。

举例：

`ffprobe -of xml -show_streams in.mp4` 将得到XML格式的输出；

`ffprobe -of json -show_streams in.mp4` 将得到JSON格式的输出。

<br>

### 2.2.x ffprobe字段信息说明

**packet字段说明**

| 字段          | 说明                                         |
| ------------- | -------------------------------------------- |
| codec_type    | 多媒体类型，如视频包、音频包等               |
| stream_index  | 多媒体的stream索引                           |
| pts           | 多媒体的显示时间值                           |
| pts_time      | 根据不同格式计算过后的多媒体的显示时间       |
| dts           | 多媒体解码时间                               |
| dts_time      | 根据不同格式计算过后的多媒体解码时间         |
| duration      | 多媒体包占用的时间值                         |
| duration_time | 根据不同格式计算过后的多媒体包所占用的时间值 |
| size          | 多媒体包的大小                               |
| pos           | 多媒体包所在文件偏移位置                     |
| flags         | 多媒体包标记，如关键包与非关键包的标记       |

<br>

**format字段说明**

| 字段             | 说明                 |
| ---------------- | -------------------- |
| filename         | 文件名               |
| nb_streams       | 媒体中包含的流的个数 |
| nb_programs      | 节目数               |
| format_name      | 使用的封装模块的名称 |
| format_long_name | 封装的完整名称       |
| start_time       | 媒体文件的起始时间   |
| duration         | 媒体文件的总时间长度 |
| size             | 媒体文件的大小       |
| bit_rate         | 媒体文件的码率       |

<br>

**frame字段说明**

| 属性       | 说明                           | 值    |
| ---------- | ------------------------------ | ----- |
| media_type | 帧的类型（视频、音频、字幕等） | video |

<br>

**stream字段说明**

| 属性 | 说明 | 值   |
| ---- | ---- | ---- |
|      |      |      |

<br>

## 2.3 ffplay常用命令



<br>