## 1.简介

[PaddleX](https://github.com/PaddlePaddle/PaddleX)，依托于PaddleDetection的先进技术，构建了目标检测领域的**低代码全流程**开发范式。通过低代码开发，可实现简单且高效的模型使用、组合与定制。这将显著**减少模型开发的时间消耗**，**降低其开发难度**，大大加快模型在行业中的应用和推广速度。特色如下：

* 🎨 模型丰富一键调用：将通用目标检测、小目标检测、实例分割、行人属性识别、车辆属性识别涉及的**61个模型**整合为5条模型产线，通过极简的**Python API一键调用**，快速体验模型效果。此外，同一套API，也支持图像分类、图像分割、文本图像智能分析、通用OCR、时序预测等共计**200+模型**，形成20+单功能模块，方便开发者进行**模型组合使用**。

* 🚀提高效率降低门槛：提供基于**统一命令**和**图形界面**两种方式，实现模型简洁高效的使用、组合与定制。支持**高性能部署、服务化部署和端侧部署**等多种部署方式。此外，对于各种主流硬件如**英伟达GPU、昆仑芯、昇腾、寒武纪和海光**等，进行模型开发时，都可以**无缝切换**。
  
## 2.能力支持

PaddleX中目标检测的4条产线均支持本地**快速推理**，部分产线支持**在线体验**，您可以快速体验各个产线的预训练模型效果，如果您对产线的预训练模型效果满意，可以直接对产线进行[高性能部署](./pipeline_deploy/high_performance_deploy.md)/[服务化部署](./pipeline_deploy/service_deploy.md)/[端侧部署](./pipeline_deploy/lite_deploy.md)，如果不满意，您也可以使用产线的**二次开发**能力，提升效果。



此外，PaddleX为开发者提供了基于[云端图形化开发界面](https://aistudio.baidu.com/pipeline/mine)的全流程开发工具, 详细请参考[教程《零门槛开发产业级AI模型》](https://aistudio.baidu.com/practical/introduce/546656605663301)


<table >
    <tr>
        <th>模型产线</th>
        <th>在线体验</th>
        <th>快速推理</th>
        <th>高性能部署</th>
        <th>服务化部署</th>
        <th>端侧部署</th>
        <th>二次开发</th>
        <th><a href = "https://aistudio.baidu.com/pipeline/mine">星河零代码产线</a></td>
    </tr>
    <tr>
        <td>通用目标检测</td>
        <td><a href = "https://aistudio.baidu.com/community/app/70230/webUI?source=appMineRecent">链接</a></td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
    </tr>
        <tr>
        <td>小目标检测</td>
        <td>🚧</td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
        <td>🚧</td>
        <td>✅</td>
        <td>🚧</td>
    </tr>
        <tr>
        <td>通用实例分割</td>
        <td><a href = "https://aistudio.baidu.com/community/app/100063/webUI?source=appMineRecent">链接</a></td>
        <td>✅</td>
        <td>✅</td>
        <td>✅</td>
        <td>🚧</td>
        <td>✅</td>
        <td>✅</td>
    </tr>
        

    
</table>



> ❗注：以上功能均基于GPU/CPU实现。PaddleX还可在昆仑、昇腾、寒武纪和海光等主流硬件上进行快速推理和二次开发。下表详细列出了模型产线的支持情况，具体支持的模型列表请参阅[模型列表(MLU)](./other_devices_support/model_list_mlu.md)/[模型列表(NPU)](./other_devices_support/model_list_npu.md)/[模型列表(XPU)](./other_devices_support/model_list_xpu.md)/[模型列表DCU](./other_devices_support/model_list_dcu.md)中的OCR相关模块。我们正在适配更多的模型，并在主流硬件上推动高性能和服务化部署的实施。


<details>
  <summary>👉 国产化硬件能力支持</summary>

<table>
  <tr>
    <th>产线名称</th>
    <th>昇腾 910B</th>
    <th>昆仑 R200/R300</th>
    <th>寒武纪 MLU370X8</th>
    <th>海光 Z100</th>
  </tr>
  <tr>
    <td>通用目标检测</td>
    <td>✅</td>
    <td>✅</td>
    <td>✅</td>
    <td>🚧</td>
  </tr>
  <tr>
    <td>通用实例分割</td>
    <td>✅</td>
    <td>🚧</td>
    <td>✅</td>
    <td>🚧</td>
  </tr>
</table>
</details>

## 3.模型列表


## 主体检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|PP-ShiTuV2_det|41.5|33.7426|537.003|27.6 M|

**注：以上精度指标为 [PaddleClas主体检测数据集](https://github.com/PaddlePaddle/PaddleClas/blob/release/2.5/docs/zh_CN/training/PP-ShiTu/mainbody_detection.md) mAP(0.5:0.95)。**

## 目标检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|Cascade-FasterRCNN-ResNet50-FPN|41.1|-|-|245.4 M|
|Cascade-FasterRCNN-ResNet50-vd-SSLDv2-FPN|45.0|-|-|246.2 M|
|CenterNet-DLA-34|37.6|-|-|75.4 M|
|CenterNet-ResNet50|38.9|-|-|319.7 M|
|DETR-R50|42.3|59.2132|5334.52|159.3 M|
|FasterRCNN-ResNet34-FPN|37.8|-|-|137.5 M|
|FasterRCNN-ResNet50-FPN|38.4|-|-|148.1 M|
|FasterRCNN-ResNet50-vd-FPN|39.5|-|-|148.1 M|
|FasterRCNN-ResNet50-vd-SSLDv2-FPN|41.4|-|-|148.1 M|
|FasterRCNN-ResNet50|36.7|-|-|120.2 M|
|FasterRCNN-ResNet101-FPN|41.4|-|-|216.3 M|
|FasterRCNN-ResNet101|39.0|-|-|188.1 M|
|FasterRCNN-ResNeXt101-vd-FPN|43.4|-|-|360.6 M|
|FasterRCNN-Swin-Tiny-FPN|42.6|-|-|159.8 M|
|FCOS-ResNet50|39.6|103.367|3424.91|124.2 M|
|PicoDet-L|42.6|16.6715|169.904|20.9 M|
|PicoDet-M|37.5|16.2311|71.7257|16.8 M|
|PicoDet-S|29.1|14.097|37.6563|4.4 M |
|PicoDet-XS|26.2|13.8102|48.3139|5.7M |
|PP-YOLOE_plus-L|52.9|33.5644|814.825|185.3 M|
|PP-YOLOE_plus-M|49.8|19.843|449.261|83.2 M|
|PP-YOLOE_plus-S|43.7|16.8884|223.059|28.3 M|
|PP-YOLOE_plus-X|54.7|57.8995|1439.93|349.4 M|
|RT-DETR-H|56.3|114.814|3933.39|435.8 M|
|RT-DETR-L|53.0|34.5252|1454.27|113.7 M|
|RT-DETR-R18|46.5|19.89|784.824|70.7 M|
|RT-DETR-R50|53.1|41.9327|1625.95|149.1 M|
|RT-DETR-X|54.8|61.8042|2246.64|232.9 M|
|YOLOv3-DarkNet53|39.1|40.1055|883.041|219.7 M|
|YOLOv3-MobileNetV3|31.4|18.6692|267.214|83.8 M|
|YOLOv3-ResNet50_vd_DCN|40.6|31.6276|856.047|163.0 M|
|YOLOX-L|50.1|185.691|1250.58|192.5 M|
|YOLOX-M|46.9|123.324|688.071|90.0 M|
|YOLOX-N|26.1|79.1665|155.59|3.4M|
|YOLOX-S|40.4|184.828|474.446|32.0 M|
|YOLOX-T|32.9|102.748|212.52|18.1 M|
|YOLOX-X|51.8|227.361|2067.84|351.5 M|

**注：以上精度指标为 **[COCO2017](https://cocodataset.org/#home)** 验证集 mAP(0.5:0.95)。**

## 小目标检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|PP-YOLOE_plus_SOD-S|25.1|65.4608|324.37|77.3 M|
|PP-YOLOE_plus_SOD-L|31.9|57.1448|1006.98|325.0 M|
|PP-YOLOE_plus_SOD-largesize-L|42.7|458.521|11172.7|340.5 M|

**注：以上精度指标为 **[VisDrone-DET](https://github.com/VisDrone/VisDrone-Dataset)** 验证集 mAP(0.5:0.95)。**

## 行人检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|PP-YOLOE-L_human|48.0|32.7754|777.691|196.1 M|
|PP-YOLOE-S_human|42.5|15.0118|179.317|28.8 M|

**注：以上精度指标为 **[CrowdHuman](https://bj.bcebos.com/v1/paddledet/data/crowdhuman.zip)** 验证集 mAP(0.5:0.95)。**

## 车辆检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|PP-YOLOE-L_vehicle|63.9|32.5619|775.633|196.1 M|
|PP-YOLOE-S_vehicle|61.3|15.3787|178.441|28.8 M|

**注：以上精度指标为 **[PPVehicle](https://github.com/PaddlePaddle/PaddleDetection/tree/develop/configs/ppvehicle)** 验证集 mAP(0.5:0.95)。**

## 人脸检测模块
|模型名称|mAP（%）|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|PicoDet_LCNet_x2_5_face|35.8|33.7426|537.003|27.7 M|

**注：以上精度指标为 **[wider_face](https://github.com/PaddlePaddle/PaddleDetection/tree/develop/configs/ppvehicle)** 评估集 mAP(0.5:0.95)。**

## 实例分割模块
|模型名称|Mask AP|GPU推理耗时（ms）|CPU推理耗时|模型存储大小（M)|
|-|-|-|-|-|
|Mask-RT-DETR-H|50.6|132.693|4896.17|449.9|
|Mask-RT-DETR-L|45.7|46.5059|2575.92|113.6|
|Mask-RT-DETR-M|42.7|36.8329|-|66.6 M|
|Mask-RT-DETR-S|41.0|33.5007|-|51.8 M|
|Mask-RT-DETR-X|47.5|75.755|3358.04|237.5 M|
|Cascade-MaskRCNN-ResNet50-FPN|36.3|-|-|254.8|
|Cascade-MaskRCNN-ResNet50-vd-SSLDv2-FPN|39.1|-|-|254.7|
|MaskRCNN-ResNet50-FPN|35.6|-|-|157.5 M|
|MaskRCNN-ResNet50-vd-FPN|36.4|-|-|157.5 M|
|MaskRCNN-ResNet50-vd-SSLDv2-FPN|38.2|-|-|157.2 M|
|MaskRCNN-ResNet50|32.8|-|-|127.8 M|
|MaskRCNN-ResNet101-FPN|36.6|-|-|225.4 M|
|MaskRCNN-ResNet101-vd-FPN|38.1|-|-|225.1 M|
|MaskRCNN-ResNeXt101-vd-FPN|39.5|-|-|370.0 M|
|PP-YOLOE_seg-S|32.5|-|-|31.5 M|

**注：以上精度指标为 **[COCO2017](https://cocodataset.org/#home)** 验证集 Mask AP(0.5:0.95)。**


>**注：以上所有模型 GPU 推理耗时基于 NVIDIA Tesla T4 机器，精度类型为 FP32， CPU 推理速度基于 Intel(R) Xeon(R) Gold 5117 CPU @ 2.00GHz，线程数为8，精度类型为 FP32。**