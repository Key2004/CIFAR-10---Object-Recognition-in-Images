## 代码结构<br>
#### 数据准备：<br>
下载了 CIFAR-10 数据集（包括训练集和测试集）并将其解压缩。
训练样本的标签存储在名为 trainLabels.csv 的 CSV 文件中。
您定义了 data_dir，用于存放数据。
标签字典：
read_csv_labels 函数读取 CSV 文件，并创建一个将图像文件名映射到其对应标签的字典。
标签表示不同的类别（例如“猫”、“狗”等）。
训练-验证集拆分：
reorg_train_valid 函数将训练数据拆分为训练集和验证集。
它确保每个类别在两个子集中都有平衡的表示。
valid_ratio 决定了分配给验证集的数据比例。
测试数据组织：
reorg_test 函数将测试数据整理为便于在预测期间访问的形式。
模型定义：
您定义了一个名为 get_net 的函数，该函数返回一个具有 10 个输出类别（用于 CIFAR-10）的 ResNet18 模型。


训练函数：
你定义了一个名为train的函数，用于训练神经网络模型。
在训练过程中，你使用了随机梯度下降（SGD）优化器，并动态调整学习率。
你还添加了L1和L2正则化项，以控制模型的复杂度。
训练过程中，你记录了训练损失、训练准确率和验证准确率，并在每个epoch结束时打印这些指标。
数据增强部分：
你定义了两个数据增强的转换：transform_train和transform_test。
transform_train包括随机旋转、随机水平翻转、颜色增强和标准化。
transform_test只包括标准化。
这些转换将应用于训练集、验证集和测试集中的图像。
如果你还有其他问题或需要更多帮助，请随时告诉我！😊
