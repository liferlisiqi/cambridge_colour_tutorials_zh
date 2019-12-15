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

支持最广泛的相机对焦模式是**单次对焦**，最适合静止物体。 单次拍摄模式容易受快速移动对象的对焦误差影响，因为它无法预期对象的运动，此外还可能使取景器中的这些移动对象难以可视化。 单次对焦需要在拍摄照片之前锁定对焦。

许多相机还支持**自动对焦模式**，该模式可以连续调整移动对象的焦距。 佳能相机将其称为“ AI伺服”对焦，而尼康相机将其称为“连续”对焦。 通过根据先前对焦距离估计物体速度，然后预测物体在之后的动作。 接下来，相机会事先对此预测距离进行对焦，以解决快门时滞（按下快门按钮和开始曝光之间的延迟）。 这大大增加了移动物体正确对焦的可能性。下面显示了各种佳能相机的最大跟踪速度：

![img](https://cdn.cambridgeincolour.com/images/tutorials/af_canonaiservoperf.png)

实际的最大跟踪速度还取决于对象移动的不规则程度、对比度和光线，镜头的类型以及用于跟踪对象的自动对焦传感器的数量。 另请注意，使用对焦跟踪会大大减少相机的电池寿命，因此请仅在必要时使用。

## AUTOFOCUS ASSIST BEAM

许多相机配备有AF辅助光束，这是一种主动自动对焦的方法，它使用可见或红外光束来帮助自动对焦传感器检测到被摄对象。 尽管自动对焦辅助光束还具有自动对焦速度较慢的缺点，但在被摄对象没有足够照明或对比度不足以进行自动对焦的情况下，这非常有用。

大多数紧凑型相机使用内置的红外光源进行AF辅助，而数码单反相机通常使用内置或外部相机闪光灯来照亮被摄对象。 当使用闪光灯进行自动对焦辅助时，如果被摄对象在两次闪光之间有明显移动，则自动对焦辅助光束可能会难以对焦。 因此，仅建议对静止物体使用自动对焦辅助光。

## IN PRACTICE: ACTION PHOTOS

使用AI伺服或连续模式时，自动对焦几乎总是在动作照片上表现最佳。 通过确保镜头不必在较大的焦距范围内进行搜索，可以大大提高聚焦性能。

实现这一目标最普遍的方法可能是将相机预先对焦在移动物体预估通过的位置附近。 在下边的骑自行车的人例子中，由于骑自行车的人可能会在该距离附近经过，因此可以在路边附近预先对焦。

![img](https://cdn.cambridgeincolour.com/images/tutorials/af_biker.jpg)

某些SLR镜头还具有最小焦距切换开关， 将其设置为可能的最大距离（假设拍摄对象永远不会更近）也可以提高性能。但是请注意，即使尚未实现对焦锁定，在连续自动对焦模式下仍可以拍摄。

## IN PRACTICE: PORTRAITS & OTHER STILL PHOTOS

最好使用单次自动对焦模式拍摄静态照片，该模式可确保在曝光开始之前已完成对焦锁定。 对比度和强光的通常对焦点要求仍然适用，尽管需要确保几乎没有物体运动。

对于人像来说，眼睛是最佳焦点，既因为这是标准设置，又因为它具有良好的对比度。 尽管中央自动对焦传感器通常最敏感，但使用偏心对象的偏心对焦点可以实现最准确的对焦。 如果改为使用中央自动对焦点来实现对焦锁定（在对偏离中心的拍摄对象进行重新构图之前），则对焦距离将始终在实际拍摄对象距离之后，并且该误差对于较近的拍摄对象会增加。 准确对焦对人像尤为重要，因为人像通常具有较浅的景深。

由于最常见的AF传感器类型是垂直线传感器，因此也需要考虑对焦点主要包含垂直对比度还是水平对比度。 在弱光条件下，在自动对焦过程中将相机旋转90°可能无法实现对焦锁定。

![img](https://cdn.cambridgeincolour.com/images/tutorials/af_horlines.jpg)

在上面的示例中，楼梯主要由水平线组成。 如果将焦点对准前景楼梯的后部（以使用超焦距最大化视场深度），则可以通过在自动对焦过程中首先将其相机置于横向模式来避免自动对焦失败。 如果需要，可以在曝光期间将相机旋转回纵向。

## reference
[understanding camera autofocus](https://www.cambridgeincolour.com/tutorials/camera-autofocus.htm)  

[tutorial on image histograms](https://www.cambridgeincolour.com/tutorials/histograms1.htm)