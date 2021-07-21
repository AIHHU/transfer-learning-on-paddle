# transfer-learning-on-paddle
在paddle静态图模式下，使用cifar10数据集对resnet50模型进行了预训练，接着改变输出层，在flower数据集上进行迁移学习
# 使用说明
1、打开百度AI studio，创建项目，环境选择paddlepaddle2.0.2

2、首先导入pretrain_cifar.ipynb并运行即可开始训练，结束后将在文件夹内得到resnet50在cifar数据集上训练得到的模型（预训练模型）

3、再导入train_flower.ipynb并运行即可开始训练，结束后便完成了迁移学习。注：可根据自身情况修改pass_id的轮数
。
4、训练完成后，自行写一个保存推理模型的代码用于推理即可

# 个人总结
1、迁移学习最好能在任务相似，且数据集相似的情况下使用

2、由于paddle.dataset里没有提供ImageNet(也可能是我没找到)，因此采用cifar数据集，由于数据集差别比较大，因此在进行迁移学习时并没有对ResNet50的参数进行固定

3、由于cifar数据集的图片大小与flower数据集不一致，因此对cifar数据集进行了上采样
