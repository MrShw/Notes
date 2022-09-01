# 一、人工智能开发库

## 1. keras

Keras是一个用Python编写的开源神经网络库，在希腊语中意为喇叭。

```
Keras 与 TensorFlow 2 一起打包为tensorflow.keras. 要开始使用 Keras，只需安装 TensorFlow 2。

Keras/TensorFlow 兼容：

Python 3.7–3.10
Ubuntu 16.04 或更高版本
Windows 7 或更高版本
macOS 10.12.6 (Sierra) 或更高版本。
```
tf.keras 主要有以下模块
```
models：模型克隆代码，以及与模型相关的API。

optimizers：内置优化器类。

preprocessing：Keras数据预处理工具。

regularizers：内置正规化器。

utils：Keras实用程序。

datasets：Keras内置数据集。

initializers：Keras初始化器序列化/反序列化。

layers：Keras层API。

losses：内置损失功能。

metrics：内置指标。
```

### 1) 图片读取处理
```
utils.load_img(
    path = "./bus/300.jpg", 
    target_size = (200, 200)
)
```
<br>

### 2) 训练设置

```
Batch，大小是在更新模型之前，处理的多个样本。当数据集很大的时候，对于每个epoch，很难将所有的数据集一次读入到内存中，这是需要将数据集分为几次读入，每次称为一个batch。模型更新多少次

batch size，即batch中样本的数量。

Epoch数是通过训练数据集的完整传递次数。
```
![imge](https://www.zhihu.com/equation?tex=%5Cmathbf%7BNumber+~+of+~+Batches+%3D+%5Cfrac%7BTraining+~+Set+~+Size%7D%7BBatch+~+Size%7D%7D)

> batch 批量，组，表示把所有样本分为多少个组，流行的批量大小包括32,64和128个样本。utils.image_dataset_from_directory

> epoch 周期，训练完所有数据为一个周期，model.fit

```
假设您有一个包含200个样本（数据行）的数据集，并且您选择的Batch size大小为5和1,000个Epoch。

这意味着数据集将分为40个Batch，每个Batch有5个样本（batch size）。每批五个样品后，模型权重将更新。

这也意味着一个epoch将涉及40个Batch或40个模型更新。

有1000个Epoch，模型将暴露或传递整个数据集1,000次。在整个培训过程中，总共有40,000Batch。
```