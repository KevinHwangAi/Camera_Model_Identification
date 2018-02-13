## Camera_Model_Identification 相机型号识别(图像识别)

#### 比赛要求:

Finding footage of a crime caught on tape is an investigator's dream. But even with crystal clear, damning evidence, one critical question always remains–is the footage real?
找到录在磁带上的犯罪片段是调查人员的梦想。但即使有清晰明了的证据，一个关键问题总是存在 - 这些镜头是真实的吗？

Today, one way to help authenticate footage is to identify the camera that the image was taken with. Forgeries often require splicing together content from two different cameras. But, unfortunately, the most common way to do this now is using image metadata, which can be easily falsified itself.
现在，帮助验证镜头的一种方法是识别图像拍摄的相机。伪造经常需要拼接来自两个不同相机的内容。但不幸的是，现在最常用的方法是使用图像元数据，而这些元数据本身很容易被伪造。

This problem is actively studied by several researchers around the world. Many machine learning solutions have been proposed in the past: least-squares estimates of a camera's color demosaicing filters as classification features, co-occurrences of pixel value prediction errors as features that are passed to sophisticated ensemble classifiers, and using CNNs to learn camera model identification features. However, this is a problem yet to be sufficiently solved.
世界各地的几位研究人员正在积极研究这个问题。过去已经提出了许多机器学习解决方案：相机的颜色去马赛克滤波器的最小二乘估计作为分类特征，将像素值预测误差的共同出现作为传递给复杂的整体分类器的特征，并且使用cnns学习相机模型识别功能。然而，这是一个尚未得到充分解决的问题。

For this competition, the IEEE Signal Processing Society is challenging you to build an algorithm that identifies which camera model captured an image by using traces intrinsically left in the image. Helping to solve this problem would have a big impact on the verification of evidence used in criminal and civil trials and even news reporting.
在这场比赛中，IEEE信号处理协会正在挑战您构建一种算法，通过使用图像中原本留下的迹线来识别哪个相机模型拍摄了图像。帮助解决这个问题会对验证刑事和民事审判中使用的证据甚至新闻报道产生重大影响。

#### [传送门](https://www.kaggle.com/c/sp-society-camera-model-identification#description)


#### 比赛心得:

这次比赛,是我首次参加Kaggle上的图像识别类的数据竞赛(因之前一直使用Macbook).

这次使用的电脑硬件是i7-4770 16G Gtx960Ti,计算机的GPU算力非常一般,所以只能使用迁移学习进行建模与训练.

深度学习框架:Keras,
CNN模型:Resnet50
训练图片集:2,750张(原始数据)
Data Augmentation:将图片训练集增加至22,000张 (但因内存不足,最后只使用了一半的数据作训练.这个版本还没有使用生产器来传入数据,下个版本改进.)
batch_size:60
epoch:100

跑了约5个多小时,期间修改模型一次停了,最后提交Kaggle的test结果为55.3%.

如果有比较好的电脑配置,可以试试将训练集增加更多,和使用层数更多的卷积模型.(攒钱等升级1080Ti x 4后,再折腾个高点的精度...CNN就是个壕的东西)
