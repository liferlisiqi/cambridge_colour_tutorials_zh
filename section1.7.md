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

## FACTORS AFFECTING AUTOFOCUS PERFORMANCE

摄影对象可能会对相机的自动对焦效果产生巨大影响，而且其影响通常甚至超过相机型号，镜头或对焦设置之间的任何变化。 影响自动对焦的三个最重要的因素是：光线水平，拍摄对象对比度以及相机或拍摄对象的运动。

![img](https://raw.githubusercontent.com/liferlisiqi/cambridge_colour_tutorials_zh/master/jpg/1.7_autofocus_factors.PNG)

上面的例子说明了不同焦点的质量，请注意每个因素都不是独立的。 换句话说，即使相似的对象也具有极高的对比度，即使是昏暗的物体，也可以实现自动对焦。 这对选择自动对焦点有重要意义：假设所有其他因素保持相等，选择边缘锐利或纹理明显的对焦点可以实现更好的自动聚焦。

在左侧的示例中，幸运的是对焦效果最佳的位置也是拍摄对象的位置。 下一个示例更具问题，因为自动对焦在背景而非主体上表现最佳。 

![demosaic](https://raw.githubusercontent.com/liferlisiqi/cambridge_colour_tutorials_zh/master/jpg/1.7_autofocus_factors2.png)

在上边的照片中，如果对焦在被摄对象后面快速移动的光源，那么当景深较浅时（低亮场景就是这样），这样对焦就会造成被摄对象失焦。因此在对象的外部高亮区域对焦可能是最好的方法，但要注意的是，根据移动光源的位置，高亮部分会迅速改变表面和光强。

如果相机难以对焦在外部高亮区域，则对象的脚或者地上的叶子等对比度较低的区域将会成为对焦点。使上述选择变得困难的原因是，这些决策通常必须在不到一秒钟的时间内做出。 在本教程结束时，将在它们各自的部分中讨论用于在静止和运动对象上的自动对焦特定技术。

## NUMBER & TYPE OF AUTOFOCUS POINTS

自动对焦的鲁棒性和灵活性主要取决于相机提供的自动对焦点的数量、位置和类型。 高端SLR相机可以具有45个或更多的自动对焦点，而其他相机可能只有一个中央自动对焦点。 自动对焦传感器的两个示例布局如下所示：

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray1.png" height="100px" alt="Low Noise(Smooth Colorless Gray)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray2.png" height="100px" alt="High Noise(Patches of Color)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray3.png" height="100px" alt="High Noise(Patches of Color)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray4.png" height="100px" alt="High Noise(Patches of Color)" >
</div>

高端单反相机，从左到右的光圈值依次为：f/2.8,f/4.0,f/5.6,f/8.0 

<div align="center">
<img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray1b.png" height="100px" alt="Low Noise(Smooth Colorless Gray)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray2b.png" height="100px" alt="High Noise(Patches of Color)" ><img src="https://cdn.cambridgeincolour.com/images/tutorials/af_focusarray3b.png" height="100px" alt="High Noise(Patches of Color)" >
</div>

入门级单反相机，从左到右光圈值依次为：f/2.8,f/4.0,f/5.6

两种类型的对焦传感器:
 \+ **cross-type sensors** (二维对比度传感器，精度高)
 l **vertical line sensors** (一维对比度传感器，精度低)

对于SLR相机，自动对焦点的数量和精度会根据所用镜头的最大光圈而变化。如上所述， 选择相机镜头时，这是一个重要的考虑因素：即使您不打算以最大光圈使用镜头，但该光圈仍然可以帮助相机获得更好的对焦精度。 此外，由于中央自动对焦传感器几乎总是最准确的，因此对于偏心拍摄对象，通常最好首先使用该传感器来实现对焦锁定（在重新构图之前）。

多个自动对焦点可以协同工作以提高可靠性，也可以单独工作以提高特异性，具体取决于您选择的相机设置。 某些相机还具有用于集体照的“自动景深”功能，以确保对焦点集群都在可接受的焦点范围内。

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