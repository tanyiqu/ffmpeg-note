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

<br>

### 2.2.3 查看多媒体数据包信息

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

其中packet字段说明如下：

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

## 2.3 ffplay常用命令



<br>