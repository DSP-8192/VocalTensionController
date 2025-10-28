# VocalTensionController
一个可以控制人声张力的工具\
视频演示：https://www.bilibili.com/video/BV1FksrzAEBN/

## 使用方法
### 1. 安装PlugData
https://plugdata.org/
### 2. 将人声分成谐波和气声两个轨道
这一步很重要。如果歌声合成引擎不能单独生成谐波（harmonics）和气声（air/noise），可以自行搜索分离算法。个人推荐这个https://github.com/yxlllc/vocal-remover
### 3. 在谐波轨挂载PlugData，并打开本工程
### 4. 调整旋钮以控制人声张力
切换到run mode，旋转中间的旋钮\
或者添加自动化参数，选择`tension`，范围是`(-100,100)`，`0`表示与输入相同

## 工作原理
先提取人声F0，然后设计频域的filter，与输入人声的频谱相乘，最后做Inverse FFT\
低张力增强F0，削弱泛音（overtone）；高张力削弱F0，增强泛音

## 参数
Block size为2048（在44.1KHz采样率下约0.046秒），Hann window，50%重叠\
**仅支持单声道，会对立体声输入做`(L+R)/2`的处理，请在涉及立体声效果的插件之前挂载此工具**

## 可能的后续工作
完善GUI\
使block size成为用户可调参数\
集成谐波气声分离算法\
编译成VST插件\
（技术力有限，哪位大手子有兴趣可以搞一下）
