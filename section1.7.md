# Understanding camera autofocus

[原文连接](https://www.cambridgeincolour.com/tutorials/camera-autofocus.htm)  

相机的自动对焦系统会智能地调节相机镜头，以对被摄物体聚焦，这可能意味着清晰照片和错失机会之间的差异。 尽管目标似乎很简单（在焦点处很锐利），但是相机对焦的内部工作原理并不是那么简单。 本教程旨在通过介绍自动对焦的工作原理来改善您的照片，从而使您能够充分利用其自动对焦功能并避免其缺点。

注意：自动对焦（AF）可以通过使用相机内的对比度传感器（被动AF）或通过发出信号来照亮或估计与被摄对象的距离（主动AF）来工作。 可以使用对比度检测或相位检测方法执行被动自动对焦，但是两者都依靠对比度来实现精确的自动对焦。 因此，就教程认为它们的成像质量是相似的。 除非另有说明，否则本教程将假定为被动自动对焦。 我们还将在最后讨论主动自动对焦的AF辅助光束方法。

## CONCEPT: AUTOFOCUS SENSORS

相机的自动对焦传感器是实现精确对焦的真正引擎，并且根据图像视场以各种阵列形式存在。 每个传感器通过评估图像在其相应点的对比度变化来测量相应的焦点，假定最大对比度对应于最大清晰度。

![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swan1b.jpg)



| ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm3.png) 400% | ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm3hist.png) ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_histgrad128.jpg) Sensor Histogram |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm2.png) 400% | ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm2hist.png) ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_histgrad128.jpg) Sensor Histogram |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm1.png) 400% | ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_swanzm1hist.png) ![img](https://cdn.cambridgeincolour.com/images/tutorials/af_histgrad128.jpg) Sensor Histogram |

自动对焦的过程通常如下：
**（1）**自动对焦处理器（AFP）轻微改动对焦距离
**（2）**AFP读取AF传感器，以评估是否完成对焦以及对焦程度。
**（3）**使用（2）中的信息，AFP重新设置镜头的对焦距离。
**（4）**重复步骤2-3，直到获得令人满意的对焦为止。

整个过程通常在一秒钟之内完成。 对于困难的对象，相机可能无法获得令人满意的对焦，并且会放弃重复上述步骤，从而导致自动对焦失败。 这是可怕的“拉风箱”场景，在这种情况下，相机反复来回聚焦，而没有实现对焦锁定。 但是这并不意味着无法针对所选对象进行对焦， 自动对焦是否会失败以及为什么会失败的主要决定因素在下一节进行介绍。

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/wb_mixed-ex2.jpg" height="500px" alt="Low Noise(Smooth Colorless Gray)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/wb_mixed-ex.jpg" height="500px" alt="High Noise(Patches of Color)" >
</div>





## FACTORS AFFECTING AUTOFOCUS PERFORMANCE

摄影对象可能会对相机的自动对焦效果产生巨大影响，而且其影响通常甚至超过相机型号，镜头或对焦设置之间的任何变化。 影响自动对焦的三个最重要的因素是：光线水平，拍摄对象对比度以及相机或拍摄对象的运动。

![img](https://cdn.cambridgeincolour.com/images/tutorials/af_pointquality-top2.png)



![demosaic](/jpg/1.1_demosaic.png)





虽然这个方法可以达到目的，但大多数相机都会采取额外的操作来从这个颜色阵列中获取更多的信息。如果只在每个2x2阵列的原本位置利用这些颜色信息，那么我们只能得到水平/垂直上一半分辨率的图像。如果利用多个相互重叠的2x2阵列来进行插值计算，就能实现更高的分辨率，如下图所示。

## NUMBER & TYPE OF AUTOFOCUS POINTS

![demosaic2](/jpg/1.1_demosaic2.png)

去马赛克的算法有很多，在这里介绍的算法在计算过程中不会考虑使用图像边缘的信息。如果我们假设图像在每个方向上是连续的，那么边缘附近的计算就不准确。而对于数百万像素的相机，这些边缘附近的像素经常会被剪切掉，所以损失通常可以忽略不记。

## AF MODE: CONTINUOUS & AI SERVO vs. ONE SHOT

当图像中具有接近分辨率极限的小尺寸细节纹理时，传感器有时会骗过去马赛克算法，产生不符实际的结果，也叫做artifact。最常见的一种摩尔纹，表现形式为重复图案、颜色失真或者迷宫格。

![demosaic_artifact](/jpg/1.1_demosaic_artifact.png)

上面展示了两个不同放大倍数的照片，可以看到下面四个图都出现了摩尔纹，而且在第三个图中还出现了迷宫格和彩噪，这些artifacts的出现取决于纹理类型和处理RAW图的方法。

然而即使是理论上完美的传感器，可以捕获并区分感光点的所有颜色，摩尔纹和其他artifacts仍然会出现，这是所有以离散间隔或位置对连续信号进行采样的系统不可避免的后果。所以几乎所有数字传感器都包含称为光学低通滤波器（OLPF）或扛混叠滤波器（AA）的东西，通常是放在传感器上面的薄层，它通过对超过传感器分辨率的问题细节进行有效模糊来缓解artifacts。

## AUTOFOCUS ASSIST BEAM

你可能疑惑本文中第一幅图的感光点为什么没有紧紧放置在彼此旁边，实际上相机传感器上的感光点并没有覆盖整个表面，为了容纳其他电子设备，可能仅仅占据总面积的一半。如下图所示，感光点之间会有“小尖峰”来将光子引导到其中一个感光点。数码相机在每个感光点上方都包含微透镜（microlens）以增强聚光能力，这些透镜类似于漏斗，将本可能会被浪费的光子引导到感光点。

![microlens](/jpg/1.1_microlens.png)

精心设计的微透镜可以增强每个感光点的光信号，进而可以在相同曝光时间内生成具有更少噪声的图像。相机厂商已经能够通过改善微透镜的设计来减少最高分辨率下的噪声，尽管同样面积的sensor被塞进越来越多越来越小的感光点。

## IN PRACTICE: ACTION PHOTOS





## IN PRACTICE: PORTRAITS & OTHER STILL PHOTOS



## reference
[understanding camera autofocus](https://www.cambridgeincolour.com/tutorials/camera-autofocus.htm)  

[tutorial on image histograms](https://www.cambridgeincolour.com/tutorials/histograms1.htm)