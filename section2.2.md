# TUTORIALS: SHARPNESS



[原文连接](https://www.cambridgeincolour.com/tutorials/sharpness.htm)  

清晰度描述照片中细节的清晰度，并且可以成为强调纹理的有价值的创意工具。 正确的摄影和后处理技术可以大大提高清晰度，尽管清晰度最终会受到相机设备、图像放大率和视角距离的限制。 影响图像清晰度的两个基本因素：分辨率和锐利度。



<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_acutancebars.gif" height="300px" alt="high acutance" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_acutancebars2.gif" height="300px" alt="low acutance" >
</div>

锐利度描述了图像边缘信息的过渡速度如何，高锐利度会有清晰的过渡和细节。

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_resbars.png" height="300px" alt="high resolution" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_resbars2.png" height="300px" alt="low resolution" >
</div>

分辨率描述了相机区分细微间隔的细节元素的能力，例如上面显示的两组线。

对于数码相机，分辨率受数子传感器的限制，而清晰度则取决于镜头的质量和后处理的类型。 锐利度是在拍摄完照片后仍然可以控制的唯一因素，因此锐利度会在对图像进行数字锐化时得到增强。

## COMPARISON

清晰的照片要有很高的锐度和分辨率，通过下面的例子来对两个因素有个直观的了解：





![Sharpness Example: Acutance and Resolution](https://cdn.cambridgeincolour.com/images/tutorials/sharpness_ex1.jpg)

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_acutanceex.jpg" height="300px" alt="high resolution" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_resolutionex.jpg" height="300px" alt="low resolution" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/sharpness_bothex.jpg" height="300px" alt="low resolution" >
</div>

虽然这个方法可以达到目的，但大多数相机都会采取额外的操作来从这个颜色阵列中获取更多的信息。如果只在每个2x2阵列的原本位置利用这些颜色信息，那么我们只能得到水平/垂直上一半分辨率的图像。如果利用多个相互重叠的2x2阵列来进行插值计算，就能实现更高的分辨率，如下图所示。

![demosaic2](/jpg/1.1_demosaic2.png)

去马赛克的算法有很多，在这里介绍的算法在计算过程中不会考虑使用图像边缘的信息。如果我们假设图像在每个方向上是连续的，那么边缘附近的计算就不准确。而对于数百万像素的相机，这些边缘附近的像素经常会被剪切掉，所以损失通常可以忽略不记。

## Demosaicing artifacts

当图像中具有接近分辨率极限的小尺寸细节纹理时，传感器有时会骗过去马赛克算法，产生不符实际的结果，也叫做artifact。最常见的一种摩尔纹，表现形式为重复图案、颜色失真或者迷宫格。

![demosaic_artifact](/jpg/1.1_demosaic_artifact.png)

上面展示了两个不同放大倍数的照片，可以看到下面四个图都出现了摩尔纹，而且在第三个图中还出现了迷宫格和彩噪，这些artifacts的出现取决于纹理类型和处理RAW图的方法。

然而即使是理论上完美的传感器，可以捕获并区分感光点的所有颜色，摩尔纹和其他artifacts仍然会出现，这是所有以离散间隔或位置对连续信号进行采样的系统不可避免的后果。所以几乎所有数字传感器都包含称为光学低通滤波器（OLPF）或扛混叠滤波器（AA）的东西，通常是放在传感器上面的薄层，它通过对超过传感器分辨率的问题细节进行有效模糊来缓解artifacts。

## Microlens arrays

你可能疑惑本文中第一幅图的感光点为什么没有紧紧放置在彼此旁边，实际上相机传感器上的感光点并没有覆盖整个表面，为了容纳其他电子设备，可能仅仅占据总面积的一半。如下图所示，感光点之间会有“小尖峰”来将光子引导到其中一个感光点。数码相机在每个感光点上方都包含微透镜（microlens）以增强聚光能力，这些透镜类似于漏斗，将本可能会被浪费的光子引导到感光点。

![microlens](/jpg/1.1_microlens.png)

精心设计的微透镜可以增强每个感光点的光信号，进而可以在相同曝光时间内生成具有更少噪声的图像。相机厂商已经能够通过改善微透镜的设计来减少最高分辨率下的噪声，尽管同样面积的sensor被塞进越来越多越来越小的感光点。

## reference
[digital camera sensors](https://www.cambridgeincolour.com/tutorials/camera-sensors.htm)  
[wikipedia:Demosaicing](https://en.wikipedia.org/wiki/Demosaicing)  
[rawpedia:Demosaicing](https://rawpedia.rawtherapee.com/Demosaicing)   


