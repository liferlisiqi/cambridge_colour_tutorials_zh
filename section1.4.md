# Depth of field

[原文连接](https://www.cambridgeincolour.com/tutorials/depth-of-field.htm)  

景深是指锐度可接受的距离范围，取决于相机型号、光圈和焦距，print size 和 viewing distance也对影响我们对精神的感知。本文旨在为摄影提供更好的指导和技术理解，并提供景深计算器，来显示它随相机设置的变化。

![dept_of_field](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_dept_of_field.png)

景深不会出现从锐利到不锐利的急剧变化，而是逐渐过渡。实际上，即使我们的眼睛或相机分辨率还未察觉，聚焦距离前方或后方内容的清晰度已经开始下降。

## Circle of confusion

![circle_of_confusion](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_circle_of_confusion.png)

由于没有严格的过渡点，因此使用“模糊圈”来定义一个点被看作不清晰时的模糊程度。当我们的眼睛感觉到模糊圈时，这个区域就不在景深范围了，这时锐度便不可接受。为清楚起见，上面的模糊圈作用被夸大了，实际只是相机传感器区域的一小部分。

![circle_of_confusion2](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_circle_of_confusion2.png)

什么时候模糊圈会被我们的眼睛所察觉呢？一个可接受锐度的模糊圈被宽泛地定义为，当放大到标准的8×10英寸印刷时会被忽视，从大约1英尺的标准距离可以察觉到。

景深仅设置为模糊圈的最大值，而不是描述失焦区域的情况，这些区域也被叫做散景（bokeh，来自日语）。具有相同景深的两幅图像可能有不同的散景，这取决于镜头的形状。实际上模糊圈通常不是圆形，当它非常小时会近似圆形，而比较大时会呈现具有5-8个边的多边形。

## Controlling depth of field

虽然打印尺寸和观看距离会影响眼睛的模糊圈大小，但是光圈和焦距是决定相机模糊圈大小的关键因素，大光圈（小F-stop）和近焦距会产生较浅的景深，下面测试焦距相同，光圈不同：

![aperture_diff](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_aperture_diff.png)

## Clarification: focal length and depth field

与普遍看法相反，焦距并不影响景深。虽然长焦镜头看似会产生更浅的景深，主要是因为长焦通常用于放大无法接近的拍摄对象。如果对于长焦和广角镜头而言，拍摄物体占据相同比例的图像尺寸，同焦距的景深几乎是恒定的。这也要求你要么更近距离使用广角，要么更远距离使用长焦，如下表所述：

![focal_length_chart](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_focal_length_chart.png)

请注意最小焦距确实有微妙的变化。这是一个真实的效果，但与光圈和聚焦距离相比可以忽略不计。即使总景深实际上是恒定的，焦距之前和之后的景深的分数也会随着焦距而变化，如下所示：

![focal_length_chart2](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_focal_length_chart2.png)

这暴露了传统DoF概念的局限性：它只考虑了总的DoF而不是它在焦平面周围的分布，尽管两者都可能有助于锐度的感知。广角镜头如何在焦平面后面提供渐渐弱化的DoF，这对于传统的风景照片来说非常重要。

较长的焦距也可能看起来具有较浅的景深，因为相对于前景放大了背景（由于其较窄的视角）。这使得失焦的背景看起来更加失焦，因为模糊程度加重。但这是另一个概念，因为景深仅描述照片的锐利区域，而不是模糊区域。

另一方面，当站在相同位置并聚焦在相同距离的物体上时，较长焦距的镜头将具有较浅的景深（即使图像将完全不同地构图对象）。这更能接近日常使用，由于更高的放大倍数，而不是焦距。

单反相机的景深也比紧凑型数码相机更浅，因为单反相机需要更长的焦距才能实现相同的视野。

## Calculating depth of field

为了计算景深，需要首先确定最大允许模糊圈值。这取决于相机类型（传感器或胶片尺寸）以及观看距离/打印尺寸组合。提前知道做什么通常并不简单，可以尝试使用景深计算器工具来帮助计算。

## Depth of focus & aperture visualization

模糊圈的另一个含义是焦深的概念（也称为“焦点传播”）。它与景深不同，因为它描述了光在相机传感器上聚焦的距离，而不是拍摄物体：

![dept_of_focus](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.4_dept_of_focus.png)

关键概念是：当物体聚焦时，来自该点的光线会聚在相机传感器上的某个点上。如果光线在稍微不同的位置（到达光盘而不是光点）汇聚传感器，则此对象将被渲染为失焦，而且程度会随光线距离增加。

## Others notes

为什么不使用最小光圈（数值最大）来实现最佳景深呢？除了曝光时间长和没有三脚架之外，太小的光圈会因为衍射效应产生更大的模糊圈，而使图像变得更柔和，即使在焦平面内也是如此。随着光圈变小，衍射很快成为景深的限制因素，

对于微距摄影（高倍率），景深还受到瞳孔放大倍数的影响。对于内部对称的镜片值为1（什么值？？？），对于广角和长焦其值会更大。对于小于1的瞳孔放大率，实现了更大的景深（比通常计算的更大），而当瞳孔放大率等于1时，瞳孔放大率不改变计算。问题在于镜头制造商通常不提供瞳孔放大率，并且人们只能在视觉上粗略估计它。

## Reference

[Understanding image sharpness part 6: Depth of field and diffraction](http://www.normankoren.com/Tutorials/MTF6.html)
[compares the depth of field for several focal lengths](https://luminous-landscape.com/dof2/) [confusion circle](https://en.wikipedia.org/wiki/Circle_of_confusion)
[Depth of Field and Depth of Focus](https://www.edmundoptics.com/resources/application-notes/imaging/depth-of-field-and-depth-of-focus/)

