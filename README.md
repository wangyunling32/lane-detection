# awesome-lane-detection
+ 最近在做车道线检测、分割的工作，整理了下这方面的资料和自己的一些总结
- 首先点名推荐一篇IEEE IV 2018的优秀论文：[《LaneNet: Real-Time Lane Detection Networks for Autonomous Driving》](./1802.05591.pdf)
+ 这篇文章主要解决了车道切换以及车道数的限制的问题
- 实现方法是：通过训练神经网络进行端到端的车道检测，将车道检测作为实例分割问题来实现
+ 文章提出了 Lannet 网络结构，如下图：
 ![](./imgs/20180608161846771.jpg)
+ Lanenet 使用一个共享的encoder，对输入图像进行处理，得到2个branch：嵌入branch和语义分割的branch。嵌入branch可以将不同的车道线区分为不同的instance；因为只需要考虑车道线，因此语义分割的结果是二值化图像；然后对2个branch做聚类，最终得到结果
