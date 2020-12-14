# Power-Aware Optimization for Video Coding

Hanli Wang

424

QQ:17455305

## Abstract

ME/MC: 运动估计/运动补偿，减少时域

Q/IQ：量化，反量化

DCT/IDCT：减少空间域冗余

EC：熵编码

## 视频标准制定

ITU-T国际电信联盟：H.264

ISO/IEC国际标准联盟：MPEG



SVG：可伸缩视频编码标准，可以根据分辨率、帧率等解码

MVC：多视点视频编码标准

HEVC；

VVC；

国内AVS-China编码：省去大笔专利费用

## Redundance in video

* Spatial
* Temporal

## 编码流程

将输入视频信号分成16x16像素的Macroblocks（宏块，不同的标准大小不一样）进行编码；

将第一帧图像进行量化，编码，DCT

第二帧利用第一帧的宏块，进行残差计算（残差=0，说明两个宏块一样），利用运动估计算位移即可

此外，有开关可以决定是否进行帧间编码还是帧内编码（模式决定），因为纯色图片之间的残差为0，不需要利用前一帧。总之码率最小化最优。

## 相关技术

### 颜色空间

将RGB颜色空间转为YCbCr，因为人眼更看重明度信息。

YCbCr3种类型：4:2:0，4:2:2，4:4:4

### 帧

I-Frame：单帧编码，常用的每15帧设置一个i帧

P-Frame：前向帧编码

B-Frame：利用前后双向帧进行编码

### 运动估计

tradeoff：拉格朗日算子算最大值

不同的标准按照不同的宏块进行匹配，宏块越大，匹配精度低，单运动编码少，反之则反。

## H.264

> 背景：coding complexity v.s. video quality/coding efficiency

