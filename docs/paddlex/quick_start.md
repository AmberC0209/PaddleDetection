# 快速开始

**说明：**

* [PaddleX](https://github.com/PaddlePaddle/PaddleX)，依托于PaddleDetection的先进技术，支持了目标检测领域的**低代码全流程**开发能力。通过低代码开发，可实现简单且高效的模型使用、组合与定制，详细请参考[PaddleOCR低代码全流程开发概览](./overview.md)。

* 在PaddleX中，我们致力于实现产线级别的训练、推理与部署，产线是指一系列预定义好的、针对特定AI任务的开发流程，其中包含能够独立完成某类任务的单模型（单功能模块）组合。本文档提供**产线**的快速使用方式，单功能模块的快速使用请参考[相关模块教程](#-更多)中的**快速集成**教程。



### 🛠️ 安装

> ❗安装PaddleX前请先确保您有基础的**Python运行环境**。

* **安装PaddlePaddle**
```bash
# cpu
python -m pip install paddlepaddle

# gpu，该命令仅适用于 CUDA 版本为 11.8 的机器环境
 python -m pip install paddlepaddle-gpu==3.0.0b1 -i https://www.paddlepaddle.org.cn/packages/stable/cu118/

# gpu，该命令仅适用于 CUDA 版本为 12.3 的机器环境
 python -m pip install paddlepaddle-gpu==3.0.0b1 -i https://www.paddlepaddle.org.cn/packages/stable/cu123/
```
> ❗ 更多飞桨 Wheel 版本请参考[飞桨官网](https://www.paddlepaddle.org.cn/install/quick?docurl=/documentation/docs/zh/install/pip/linux-pip.html)。


* **安装PaddleX**

```bash
pip install https://paddle-model-ecology.bj.bcebos.com/paddlex/whl/paddlex-3.0.0.beta1-py3-none-any.whl
```
  
> ❗ 更多安装方式参考[PaddleX安装教程](./installation/installation.md)

### 💻 命令行使用

一行命令即可快速体验产线效果，统一的命令行格式为：

```bash
paddlex --pipeline [产线名称] --input [输入图片] --device [运行设备]
```

只需指定三个参数：
* `pipeline`：产线名称
* `input`：待处理的输入图片的本地路径或URL
* `device`: 使用的GPU序号（例如`gpu:0`表示使用第0块GPU），也可选择使用CPU（`cpu`）



各产线的命令行使用，只需将`pipeline`参数调整为相应产线的名称。下面列出了每个产线对应的命令：


| 产线名称      | 使用命令                                                                                                                                                                                             |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 通用目标检测    | `paddlex --pipeline object_detection --input https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/general_object_detection_002.png --device gpu:0`                                   |
| 通用实例分割    | `paddlex --pipeline instance_segmentation --input https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/general_instance_segmentation_004.png --device gpu:0`                         |
| 小目标检测     | `paddlex --pipeline smallobject_detection --input https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/garbage_demo.png --device gpu:0`                                              |


### 📝 Python脚本使用

几行代码即可完成产线的快速推理，统一的Python脚本格式如下：
```python
from paddlex import create_pipeline

pipeline = create_pipeline(pipeline=[产线名称])
output = pipeline.predict([输入图片名称])
for batch in output:
    for item in batch:
        res = item['result']
        res.print()
        res.save_to_img("./output/")
        res.save_to_json("./output/")
```
执行了如下几个步骤：

* `create_pipeline()` 实例化产线对象
* 传入图片并调用产线对象的`predict` 方法进行推理预测
* 对预测结果进行处理

其他产线的Python脚本使用，只需将`create_pipeline()`方法的`pipeline`参数调整为相应产线的名称。下面列出了每个产线对应的参数名称及详细的使用解释：

| 产线名称     | 对应参数                 | 详细说明 |
|----------|----------------------|------|
| 通用目标检测       | `object_detection` | [通用目标检测产线Python脚本使用说明](./pipeline_usage/object_detection.md) |
| 通用实例分割       | `instance_segmentation` | [通用实例分割产线Python脚本使用说明](./pipeline_usage/instance_segmentation.md) |
| 小目标检测         | `smallobject_detection` | [小目标检测产线Python脚本使用说明](./pipeline_usage/small_object_detection.md) |

## 🌟 更多
PaddleX的各个产线均支持**在线体验**和本地**快速推理**，您可以快速体验各个产线的预训练效果，如果您对产线的预训练效果满意，可以直接对产线进行[高性能部署](./pipeline_deploy/high_performance_deploy.md)/[服务化部署](./pipeline_deploy/service_deploy.md)/[端侧部署](./pipeline_deploy/lite_deploy.md)，如果不满意，您也可以对产线进行**二次开发**提升产线效果。

此外，PaddleX为OCR相关的每个产线和单功能模块都提供了详细的开发教程，您可以根据需要选择对应的产线或模块进行开发：

产线列表：

* [通用目标检测](./pipeline_usage/object_detection.md)
* [通用小目标检测](./pipeline_usage/small_object_detection.md)
* [通用实例分割](./pipeline_usage/instance_segmentation.md)


单功能模块：

* [人脸检测模块使用教程](./module_usage/face_detection.md)
* [行人检测模块使用教程](./module_usage/human_detection.md)
* [实例分割模块使用教程](./module_usage/instance_segmentation.md)
* [主体检测模块使用教程](./module_usage/mainbody_detection.md)
* [通用目标检测模块使用教程](./module_usage/object_detection.md)
* [小目标检测模块使用教程](./module_usage/small_object_detection.md)
* [车辆检测模块使用教程](./module_usage/vehicle_detection.md)
