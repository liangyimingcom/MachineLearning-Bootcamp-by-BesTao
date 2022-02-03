# BesTao的MachineLearning Bootcamp 学习课程



如何阅读MD文档？下载typora免费的beta版本：https://typora.io/releases/all



## 一、背景



课程设计理念：

1. 不谈ML原理，专注工程落地实践；
2. 以DEMO理解为主，模拟实战应用；
3. 学习曲线可以顺畅延伸到真实世界业务和具体项目；



基于以上理念，MachineLearning入门学习课程关注两个非常成熟的部分：

- XGBoost 经典机器学习分类与排序
- CV 计算机视觉(Computer Vison)

XGBoost可以覆盖数据分类和排序的模型需求（虽然简陋但是有效），CV可以覆盖大部分图像视频模型的需求。以此作为基础，可以快速入门其他ML算法；



## 二、环境准备

1）实验账号：

2）动手实验名称

3）Juypter源码

4）Workshop网址





## 三、XGBoost 经典机器学习分类与排序



**实验：使用 XGBoost 预测客户流失情况**

使用 **Amazon SageMaker** 来解决端到端机器学习问题：即学习使用 Amazon SageMaker 创建、优化和部署机器学习 (ML) 模型，以预测移动电话服务提供商的客户流失情况。

 

<u>目标</u>

1. 在本实验中，您将：
2. 准备数据集以供训练
3. 训练和评估模型
4. 自动优化模型
5. 让模型做好部署准备前提条件



 <u>SageMaker + XGBoost的机器学习生命周期</u>

在本教程中，您将了解的部分：

- 训练和调整模型
- 部署模型
- 评估您的 ML 模型的性能
- 自动模型调整

[![ML生命周期](https://www.mfgee.ml/images/PredictiveMaintenance/ML%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)](https://www.mfgee.ml/images/PredictiveMaintenance/ML生命周期.png)



<u>本实验要求：</u> 

1. 配有运行 Microsoft Windows、Mac OS X 或 Linux (Ubuntu、SuSE 或 Red Hat) 且可以连接Wi-Fi 的笔记本电脑
2.   对于 Microsoft Windows 用户：需要拥有计算机的管理员权限。
3.   Internet 浏览器，例如 Chrome、Firefox 或 IE9（不支持旧版本 Internet Explorer）。

 

<u>场景</u>

- 失去客户对任何企业来说都是代价高昂的。尽早发现不满意的客户，您就有机会采取激励措施来留住他们。您将使用 ML 来自动发现不满意的客户，这个分析场景也称为客户流失预测。

- ML 模型很少能提供完美的预测，因此您将学习如何在不超过总 ML 成本的情况下针对预测错误进行调整。 
- 您可能对这个客户流失示例很熟悉，即客户不再使用某家移动电话服务提供商的服务，而改为使用其竞争对手的服务。如果提供商知道某位客户正在考虑弃用其服务，便可以及时采取激励措施或者升级客户所用套餐，从而鼓励客户继续使用其服务。
- 激励措施往往比失去和重新获得客户更具有成本效益



 

### 任务 **1**：访问 **Amazon SageMaker** 笔记本实例

1. 从 **Services**（服务）下拉列表中，选择 **“**机器学习” 部分中的 **Amazon SageMaker**。

2. 在左侧导航窗格中，选择 **Notebook instances**（笔记本实例）。在本实验中，我们将自动为您创建笔记本。 

3. 选择笔记本旁边的 **Open Jupyter**（打开），打开 Jupyter 控制面板。

4. 通过 Jupyter 控制面板，您可以使用 churn.txt 数据集来训练数据，以及构建、训练和部署模型。

![image-20220203150212957](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/image-20220203150212957.png)



 

### 任务 **2**：查看并完成提供的笔记本

1. 打开自动上传到 Jupyter 控制台的**xgboost_customer_churn_bootcamp_student_CN.ipynb** 笔记本文件。要完成本实验， 请从上到下仔细浏览笔记本，确保运行每个代码单元并查看其输出（这会有所帮助）。要在Jupyter 笔记本中逐步运行每个单元，请在单元中单击并按 **SHIFT+ENTER** 或选择页面顶部的 **Run**（运行）。

2.  练习方面的帮助：完成本实验中练习的方法有很多。如果您遇到问题，请查看我们针对所示问题建议的解决方案。完整答案都在 **xgboost_customer_churn_bootcamp_student_solution_CN.ipynb** 笔记本文件中，我们希望您完全用不上提供的解决方案。如果需要，请使用这些解决方案作为起点。

 

您必须进行试验，提出适合自己的解决方案。

### 练习 **1**

我们现已介绍如何完成该练习的第一部分，接下来该您完成第二部分，看看每个特征如何与我们的目标变量“流失?”关联。

您可以使用相同的 Pandas 函数 crosstab() 和 hist() 在下面的单元中输入代码来完成该练习。

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image002.jpg)

 

 

### 练习 **2**

使用 Pandas 函数 corr() 和 scatter_matrix() 来解决此问题。

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image003.jpg)

 

### 练习 **3**

完成评估程序定义。

创建 **SageMaker** 评估程序对象

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image004.jpg)

 

### 练习 **4**

使用 xgb.set_hyperparameters 来设置超参数。

**#** 设置超参数

xgb.set_hyperparameters(max_depth=5,

eta=0.2, gamma=4,

min_child_weight=6, subsample=0.8, silent=0,

objective='binary:logistic', num_round=100)

 

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image005.jpg)

  

### 练习 **5**

配置 **initial_instance_count=1** 和 **instance_type=ml.m4.xlarge**

**#** 部署模型

**Variant = 'AllTraffic'**      **#** 配置默认部署变体

xgb_predictor = xgb.deploy(initial_instance_count=1,

instance_type='ml.m4.xlarge')

 

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image006.jpg)

 

 

### 练习 **6**

HyperparameterTuner 对象通过评估程序来获取每项作业配置信息。重新创建之前创建的评估程序。

**#** 在上面重新创建评估程序

xgb = sagemaker.estimator.Estimator(container,

role, train_instance_count=1,

train_instance_type='ml.m4.xlarge', output_path='s3://{}/{}/output'.format(

bucket, prefix), sagemaker_session=sess)

 

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image007.jpg)

 

### 练习 **7**

设置作业的范围。

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image008.jpg)

 

### 练习 **8**

选择一个指标作为目标。选择一个适合二进制分类的目标。

objective_metric_name='validation:error'

 

完整格式请参考以下截图：

![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image010.jpg)

 

### 练习 **9**

创建 HyperparameterTuner 对象。必需的参数如下：

- estimator

- objective_metric_name

-  hyperparameter_ranges

- objective_type

-  max_jobs

-  max_parallel_jobs




完整格式请参考以下截图：

![image-20220203152923923](../../../../yiming/Library/Application%20Support/typora-user-images/image-20220203152923923.png)

 

 

### 练习 **10** [可放弃]

设置 AWS Auto Scaling。

 使用 Auto Scaling API 的 register_scalable_target API 方法以及 ResourceId 对应的预先计算的 resource_name。

完整格式请参考以下截图： 

 ![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image012.jpg) 





 

### 练习 **11**[可放弃]

在下面的代码中填写我们要跟踪的指标和值。您可以阅读有关 put_scaling_policy API 方法的更多信息，了解如何填写这些值。



完整格式请参考以下截图：
![img](https://raw.githubusercontent.com/liangyimingcom/storage/master/PicGo/clip_image013.jpg) 



进阶学习：





引用：

[10分钟SageMaker系列- 使用 AWS Sagemaker XGBOOSTI 模型进行房价预测.mp4](./11XGBoost 经典机器学习分类与排序/10分钟SageMaker系列- 使用 AWS Sagemaker XGBOOSTI 模型进行房价预测.mp4)



更多学习：

去Github - AWS Sample里面学习更多的demo：

[aws-samples](https://github.com/aws-samples)/[amazon-forecast-samples](https://github.com/aws-samples/amazon-forecast-samples)

https://github.com/search?q=org%3Aaws-samples+xgboost







四、



MachineLearning入门学习课程
