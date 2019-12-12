# Tutorials: white balance

[原文连接](https://www.cambridgeincolour.com/tutorials/white-balance.htm)  

白平衡（WB）是消除不真实偏色的过程，为了使在人眼呈现白色的对象在照片中也呈现白色。 正确的相机白平衡必须考虑到光源的“色温”，这是指白光的相对较暖或较冷。 我们的眼睛非常擅长判断不同光源下的白色，但是数码相机通常在自动白平衡（AWB）方面遇到很大的困难，并会产生难看的蓝色，橙色甚至绿色的偏色。 了解数字白平衡可以有助于避免这些偏色，从而在更广泛的照明条件下改善照片。

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/wb_sardmen-incorrect.jpg" height="300px" alt="Low Noise(Smooth Colorless Gray)"><img src="https://cdn.cambridgeincolour.com/images/tutorials/wb_sardmen-correct.jpg" height="300px" alt="High Noise(Patches of Color)">
</div>

## BACKGROUND: COLOR TEMPERATURE

色温描述了“黑体”表面色温的光谱， 黑体是吸收所有入射光的对象，既不反射也不允许其通过。 在我们的日常经验中，大致可以理解黑体辐射是在加热金属或石头时：当它们达到一个温度时，它们会变成“红热”，然后在更高的温度下会“白热”。 类似地，处于不同色温的黑体也具有变化的“白光”色温。 尽管叫做“白光”，但其包含成分并不一定分布在可见光谱中：

![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_bbdiagram.png)
![img](https://cdn.cambridgeincolour.com/images/tutorials/spectralsensitivity2.png)
![img](https://cdn.cambridgeincolour.com/images/tutorials/spectralsensitivity3.png)

可以看到 5000K 产生大致中性的光，而 3000K 和 9000K 分别移动以包含更多橙色和蓝色波长的光谱。 随着色温升高，颜色分布变冷。 这看似不直观，是由于较短的波长包含较高的能量。

既然摄影师不会与黑体打交道，为什么色温进行光线描述呢？ 是因为，日光和钨丝灯之类的光源紧密模仿了黑体产生的光源分布，尽管诸如荧光灯和大多数商业照明之类的其他光源远远偏离了黑体。 由于摄影师从未使用术语“色温”来指代真正的黑体光源，因此该术语隐含为与黑体颜色相似的对应色温。 下表是一些常见光源的相关色温的经验法则指南：

| **Color Temperature** | **Light Source**                       |
| --------------------- | -------------------------------------- |
| 1000-2000 K           | Candlelight                            |
| 2500-3500 K           | Tungsten Bulb (household variety)      |
| 3000-4000 K           | Sunrise/Sunset (clear sky)             |
| 4000-5000 K           | Fluorescent Lamps                      |
| 5000-5500 K           | Electronic Flash                       |
| 5000-6500 K           | Daylight with Clear Sky (sun overhead) |
| 6500-8000 K           | Moderately Overcast Sky                |
| 9000-10000 K          | Shade or Heavily Overcast Sky          |

## IN PRACTICE: JPEG & TIFF FILES

去马赛克（demosaicing）是将Bayer图转换成每个像素都包含三原色的图像的过程，如果相机不能直接测量全部色彩，那么这个过程是如何实现的呢？如果我们将每四个2x2的光腔阵列想象成一个单独的全颜色光腔，就可以解决这个问题。

| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-awb.png) | Auto White Balance |
| ------------------------------------------------------------ | ------------------ |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-custom.png) | Custom             |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-kelvin.png) | Kelvin             |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-tungsten.png) | Tungsten           |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-fluor.png) | Fluorescent        |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-daylt.png) | Daylight           |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-flash.png) | Flash              |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-cloudy.png) | Cloudy             |
| ![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_sym-shade.png) | Shade              |

虽然这个方法可以达到目的，但大多数相机都会采取额外的操作来从这个颜色阵列中获取更多的信息。如果只在每个2x2阵列的原本位置利用这些颜色信息，那么我们只能得到水平/垂直上一半分辨率的图像。如果利用多个相互重叠的2x2阵列来进行插值计算，就能实现更高的分辨率，如下图所示。

![demosaic2](/jpg/1.1_demosaic2.png)

去马赛克的算法有很多，在这里介绍的算法在计算过程中不会考虑使用图像边缘的信息。如果我们假设图像在每个方向上是连续的，那么边缘附近的计算就不准确。而对于数百万像素的相机，这些边缘附近的像素经常会被剪切掉，所以损失通常可以忽略不记。

## IN PRACTICE: THE RAW FILE FORMAT

当图像中具有接近分辨率极限的小尺寸细节纹理时，传感器有时会骗过去马赛克算法，产生不符实际的结果，也叫做artifact。最常见的一种摩尔纹，表现形式为重复图案、颜色失真或者迷宫格。

![demosaic_artifact](/jpg/1.1_demosaic_artifact.png)

上面展示了两个不同放大倍数的照片，可以看到下面四个图都出现了摩尔纹，而且在第三个图中还出现了迷宫格和彩噪，这些artifacts的出现取决于纹理类型和处理RAW图的方法。

然而即使是理论上完美的传感器，可以捕获并区分感光点的所有颜色，摩尔纹和其他artifacts仍然会出现，这是所有以离散间隔或位置对连续信号进行采样的系统不可避免的后果。所以几乎所有数字传感器都包含称为光学低通滤波器（OLPF）或扛混叠滤波器（AA）的东西，通常是放在传感器上面的薄层，它通过对超过传感器分辨率的问题细节进行有效模糊来缓解artifacts。

## CUSTOM WHITE BALANCE: CHOOSING A NEUTRAL REFERENCE

你可能疑惑本文中第一幅图的感光点为什么没有紧紧放置在彼此旁边，实际上相机传感器上的感光点并没有覆盖整个表面，为了容纳其他电子设备，可能仅仅占据总面积的一半。如下图所示，感光点之间会有“小尖峰”来将光子引导到其中一个感光点。数码相机在每个感光点上方都包含微透镜（microlens）以增强聚光能力，这些透镜类似于漏斗，将本可能会被浪费的光子引导到感光点。

![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_click.jpg)

精心设计的微透镜可以增强每个感光点的光信号，进而可以在相同曝光时间内生成具有更少噪声的图像。相机厂商已经能够通过改善微透镜的设计来减少最高分辨率下的噪声，尽管同样面积的sensor被塞进越来越多越来越小的感光点。



![img](https://cdn.cambridgeincolour.com/images/tutorials/wb_graycard.jpg)





<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/noise_20DISO100-crop.jpg" height="300px" alt="Low Noise(Smooth Colorless Gray)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/noise_epsonISO400-crop.jpg" height="300px" alt="High Noise(Patches of Color)" >
</div>



## NOTES ON AUTO WHITE BALANCE





## IN MIXED LIGHTING



## reference
[tutorials: white balance](https://www.cambridgeincolour.com/tutorials/white-balance.htm)  