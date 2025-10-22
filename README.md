# VocalTensionController
一个可以控制人声张力的工具

## 使用方法
### 1. 安装PlugData
https://plugdata.org/
### 2. 将人声分成谐波和气声两个轨道
这一步很重要。如果歌声合成引擎不能单独生成谐波和气声，可以自行搜索分离算法。个人推荐这个https://github.com/yxlllc/vocal-remover
### 3. 在谐波轨挂载PlugData，并打开本工程
### 4. 调整旋钮以控制人声张力

## 工作原理
先提取人声F0，然后设计频域的filter，与输入人声的频谱相乘，最后做Inverse FFT

## 参数
Block size为2048（在44.1KHz采样率下约0.046秒），Hann window，50%重叠

## 可能的后续工作
完善GUI\
使block size成为用户可调参数\
集成谐波气声分离算法\
编译成VST插件\
（技术力有限，哪位大手子有兴趣可以搞一下）
