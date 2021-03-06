# Camera metering & exposure

[原文连接](https://www.cambridgeincolour.com/tutorials/camera-metering.htm)  

了解相机的测光方法对于实现稳定精准的曝光具有至关重要的作用，测光系统是相机的大脑，它能够根据光照条件和ISO来决定快门速度和光圈。测光方法通常包括：部分测光（partial）、评估测光或分割测光（evaluative zone or matrix）、中央测光（center-weighted）和点测光（spot metering），他们都有各自擅长和不擅长的场景。

## Background：incident vs reflected light

所有相机的光度计都有一个根本上的缺陷：它们只能测量反射光。这也就意味着相机能做到最好的程度就是推测出有多少光线照射到物体上。

![reflected_light](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_reflected_light.png)

如果所有物体都能反射全部的入射光，那么相机就能完美的工作，但是真是世界中绝大多数物体的反射率变化很大。出于这个原因，相机内测光系统会以中度灰物体的反射光亮度为标准进行测光。如果相机对着比中度灰更亮或更暗的物体，那相机测光就会错误的计算欠曝或过曝。而手持式测光表对于同样入射光下的所有物体，都会计算出同样的曝光值。

![18%_gray](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_18gray.png)



什么是中度灰呢？在打印工业中，它被定义为反射18%入射光的油墨密度，然而相机基本不符合这个逻辑。相机的中度灰有他自己的一套理论，在这里只需要知道每个相机的中度灰会略有不同，但基本都在10-18%的反射率之间。测量物体的反射光过多或过少都会导致相机测光系统出错，不是欠曝就是过曝。

如果物体反射光的分布足够广泛，那么相机内置测光系统就会得到非常好的结果。换句话说，如果从暗到亮的分布足够均匀，那么平均反射率大致就会保持在中度灰附近。但是一些场景反射率的分布存在明显不平衡，例如雪中鸽子或者木炭上的狗。对于这个场景，相机产生图像的直方图就会位于中间调，而峰值原本应该在高光或阴影处。

## Metering options

为了准确地曝光更大范围的光照和反射组合，大多数相机都有多种测光选项。每个选项的工作原理是为不同的亮度区域分配不同的权重，权重越高的地方越可靠，对最终曝光的贡献也就越多。

![metering](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_metering.png)

白色的区域是对曝光计算贡献较大的区域，而黑色区域区域通常会被忽略（不太懂）。根据所使用的曝光项和对焦点，上述的测光图也可以偏离中心。

![meter_autofocus](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_meter_autofocus.png)

更复杂的测光算法不仅仅局限于区域映射，还包括：evaluative, zone 和 matrix metering（这里不会了），当相机设置为自动曝光时这些通常是默认设置。这些算法计算时通常将图像根据位置、光强和颜色分为多个子部分，自动对焦点的位置和相机方向也会有助于计算。

## When to use partial & spot metering

部分测光和点测光使摄影师能够更大程度地控制曝光，这也意味着至少在初学阶段难度跟高。当场景中存在相对较小的物体时，它们非常有用，你需要对其更好的曝光，或者给出最接近中度灰的配置。

部分测光最常见的场景就是逆光人像，对脸部测光可以避免曝光不足，另一方面，如果人肤色与中度灰相差很多的话，就会导致测光不准。

点测光的使用频率很低，因为测光区域很小所以针对性很强，当不确定拍摄物体反射率而使用灰卡来测光时会很有用。

![spot_metering](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_spot_metering.png)

对于创意曝光以及环境光线不常见时，点测光和局部测光也非常有用。 在下面左侧和右侧的示例中，可以从漫射的前景瓦片测光，或者从井口下方照亮的石头上测光：

![creative_exposure](https://liferlisiqi.github.io/cambridge_colour_tutorials_zh/jpg/1.3_creative_exposure.png)

## Notes on center-weighted metering

中央权重测光曾经是相机非常常见的设置，因为它可以很好的应对高动态场景，如今在灵活性方面多多少少落后于evaluative and matrix，尤其是与区域测光和点测光相比。 另一方面中央权重测光得到结果是可预测的，而evaluative and matrix模式的复杂算法则较难预测，正是由于这一点有些人仍然倾向于使用中央权重测光。

## Exposure compensation

上述所有测光模式都可以使用称为曝光补偿的特征，当此功能激活时，测光计算仍然可以继续进行，不过最终的曝光目标会通过EC值进行补偿。当观察到测光结果欠曝或过曝时，可以使用这个方法进行手动矫正。大多数相机允许最多两个stop的曝光补偿，每一级stop可以提供两倍或者一半的曝光矫正，设置为0意味着没有补偿。

曝光补偿非常适合校正由拍摄对象的反射率引起的相机内测光误差，无论使用何种测光模式，相机内测光总是会在雪景中错误地曝光诸如白鸽之类的物体，雪中的照片需要大约+1曝光补偿，而低影调图像可能需要负补偿。

在复杂光线下以RAW模式拍摄时，设置轻微的负曝光补偿（0.3-0.5）非常有用，这样可以减少高光剪裁的可能性，但仍可以增加曝光度，或者可以使用正曝光补偿来改善高光远离裁剪时的信噪比。

## Reference
[camera metering & exposure](https://www.cambridgeincolour.com/tutorials/camera-metering.htm)  
[18% Gray - The Middle Value](https://www.tonycorbell.com/blog/2016/6/14/18-gray-the-middle-value)  
[What is ‘Middle Gray’? Here’s a Short and Sweet Explanation](https://petapixel.com/2018/04/06/what-is-middle-gray-heres-a-short-and-sweet-explanation/)

[别再偷看什么50度灰了，搞摄影18度灰才是你该知道的！来瞧](https://www.jianshu.com/p/01c0c36d060c)


