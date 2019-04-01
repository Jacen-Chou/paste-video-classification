# Experimental Record——实验记录

## 20190401

3000张训练集 1000张验证集 1000张测试集

归一化参数：[0.396, 0.434, 0.435], [0.055, 0.053, 0.054]

| model | 测试集准确率 | 一个普通标题 |
| ------ | ------ | ------ |
| VGG16_bn | 94.24% |
| ResNet50 | 95.23% |
| DenseNet121 | 92.51% |

下一步考虑模型融合：
![](https://i.loli.net/2019/04/01/5ca1a42a046c7.jpg)
在这之前，要解决两个问题：
1. 证明1920*1080,batch_size=1,用一张显卡，vgg13_bn跑不了（编写代码，验证内存会溢出）
2. 证明测试集随机裁一块224*224，可能会裁到螺旋桨，导致正确率降低（用随机裁的方式，编写代码，验证正确率低的结果）