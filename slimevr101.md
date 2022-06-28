---
layout: page
nav_order: 2
---

# SlimeVR 101

{:.no_toc}

## 什么是 SlimeVR?

<!-- SlimeVR is a low cost solution to Full Body Tracking in VR. It uses forward kinematics to build a model of your skeleton calculated from the rotation of each individual tracker, with your headset and controllers being the only absolute position known. -->
SlimeVR 是一个低成本的 VR 全身动捕解决方案。它使用正向运动学来建立一个由每个单独的追踪器的旋转计算出来的骨骼模型，而你的头显和手柄是唯一已知的绝对位置。

![Skeleton tracking](assets/img/ostriches.gif)

*Gif thanks to Butterscotch. Dance thanks to Mighty*

<!-- Because the headset is a known position and rotation is derived from it, it does not require lighthouses or other forms of additional tracking to model your movement. Your headset and controllers’ built in tracking of the hands manages your shoulders and arms. SlimeVR uses data from Inertial measurement units (IMU) to determine this rotation, and the number of IMU used determines how many tracking points are available. -->
因为头显的位置是已知的，旋转是由它衍生出来的，它不需要基站或其他形式的额外追踪来模拟你的运动。你的头显和手柄的内置追踪手管理着你的肩膀和手臂。SlimeVR 使用来自惯性测量单元(IMU)的数据来确定这种旋转，所使用的IMU的数量决定了有多少追踪点可用。

## 需要多少个追踪器?

{:.no_toc}
<!-- Depending on how you plan to use FBT in VR, choose one of the following options: -->
取决于你打算如何在VR中使用全身动捕，有以下方案：

<!-- * Lower-Body Set (5 IMUs) - Your waist, legs, knees and feet are positionally tracked. Any bending of the waist or sitting down will have issues with tracking, and the orientation of your feet will not be tracked. -->
* 下半身装置(5个IMU)--你的腰部、腿部、膝盖和脚都被定位追踪。腰部的任何弯曲或坐下都会有追踪的问题，而且你的脚的方向也不会被追踪到。
<!-- * Core Set (6 IMUs) - In addition to the previous set this adds a tracker to the chest, this allows for much more accurate tracking while you're laying down, sitting or even just bending over. -->
* 核心套装(6个IMU)--除了前一套套装外，这套套装还在胸部增加了一个追踪器，这使得在你躺下、坐着甚至只是弯腰时的追踪更加精确。
<!-- * Enhanced Core Set (8 IMUs) - In addition to the previous set, you can now also wiggle your peets. If you plan on lying or sitting down a lot this adds a lot of emotiveness to your poses. -->
* 增强的核心套装(8个IMU)--除了以前的套装外，你现在还可以扭动你的同伴。如果你打算经常躺下或坐下，这将为你的姿势增加很多情感。
<!-- * Full-Body Set (10 IMUs) - In addition to the previous set, you can now move your elbows independently from your controllers in VR. Useful for dancers or additional immersion. -->
* 全身套装(10个IMU)--除了以前的套装外，现在你可以在VR中独立于控制器移动你的肘部。对舞者或额外的沉浸感很有用。

<!-- If you look at the gif above, each line there represents a tracked 'bone'. The more points of rotation you add the more defined the final tracking is, as an example the gif above only has the "Core Set" and as such there is no feet rotation. -->
如果你看一下上面的GIF，每条线都代表一个被追踪的 "骨头"。你添加的旋转点越多，最终的追踪就越明确，例如，上面的GIF只有 "核心集"，因此没有脚的旋转。

<!-- For more information on what these tracking options look like, please refer to this video: -->
关于这些追踪选项的更多信息，请参考这个视频。

<div class="video-container">
<iframe width="100%" height="auto" src="https://www.youtube.com/embed/Nl_6eQV32ys" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## 什么是扩展追踪器?

{:.no_toc}
<!-- An extension is a singular auxiliary IMU attached to a primary tracker and placed at another location. This allows you to build a secondary tracker without the need for an extra battery, charge board or microcontroller. These are sometimes referred to as AUX trackers. -->
扩展追踪器是连接到主追踪器上的一个单一的传感器，并放置在另一个位置。这使你可以建立一个辅助追踪器，而不需要额外的电池、充电板或微控制器。这些有时被称为 AUX 追踪器。

![img](https://i.imgur.com/OxED2eX.png)

*Example extension built by Rames The Generic#3540*

<!-- The length of the extension is dependent on the cabling used to connect them (shorter than 80cm is a safe range). For more information please [check the tracker schematics page.](diy/tracker-schematics.md) -->
延长线的长度取决于用于连接它们的电缆(短于80厘米是一个安全范围)。欲了解更多信息，请查看[追踪器原理图](diy/tracker-schematics.md)。

<!-- The suggested extension locations are: -->
推荐使用追踪器扩展的位置：

<!-- 1. A chest extension attached to the waist tracker.
2. A left foot extension attached to the left ankle tracker.
3. A right foot extension attached to the right ankle tracker. -->
1. 从腰部追踪器延伸到胸部。
2. 连接到左脚踝追踪器的左脚延长线。
3. 右脚延伸到右脚踝追踪器上。

<!-- On the Crowd Supply store page and on our discord server, you may find a notation that specifies the number of primary and auxiliary IMUs with a plus sign. For example, the Enhanced Core Set noted above would be called a 5+3 set up, which consists of 5 microcontrollers and 8 IMU. For a better visual on how this looks when on a person, please check the [recommended mounting points section of the server set up](server-setup/putting-on-trackers.md#recommended-mounting-points). -->
在Crowd Supply商店页面和我们的Discord服务器上，你可能会发现一个符号，用加号来说明主要和辅助IMU的数量。例如，上面提到的增强型核心套装将被称为5+3套装，它由5个微控制器和8个IMU组成。为了更好地了解这在人身上的样子，请查看[服务器设置的推荐安装点部分](server-setup/putting-on-trackers.md#recommended-mounting-points)。

<!-- Please note: building extensions is not necessary, as the foot and chest trackers will work as standalone trackers if you would prefer. However, these docs assume that you are building them as extensions. -->
请注意：扩展追踪器是不必要的，因为脚部和胸部也可以用独立的追踪器。然而，本文档假定你使用扩展追踪器。

*Created by CalliePepper#0666. Edited by Spazzwan#0001. Video created by ZRock35#9574*
