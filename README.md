# VLM4RSDet
This is the official implementation of the paper "VLM4RSDet: Collaborative Optimization with Vision-Language Model for Enhancing Remote Sensing Object Detection".
## Introduction
VLM4RSDet is a novel collaborative training framework that leverages vision-language models to enhance traditional closed-set remote sensing object detectors without introducing any additional deployment overhead.

**Abstract**: Closed-set object detection in remote sensing imagery has made significant progress, but achieving high detection accuracy remains challenging. Vision-Language Models (VLMs), which possess rich prior knowledge, offer a promising solution to this challenge. However, most existing VLMs are designed for open-vocabulary tasks and exhibit inherent limitations when directly applied to closed-set scenarios, such as notable accuracy degradation and high deployment costs. To address these issues, we propose VLM4RSDet, a novel collaborative training framework that leverages vision-language model to enhance the performance of conventional closed-set remote sensing object detectors. Notably, during inference, VLM4RSDet only retains the standard object detection architecture, thus avoiding any additional deployment overhead. Furthermore, we introduce a Global–Local Cross-Attention (GLCA) module and a Learnable Hierarchical Prediction Strategy (LHPS) to further improve collaborative training performance. Extensive experiments on five benchmark datasets demonstrate the effectiveness and robustness of our approach. In particular, our method outperforms the state-of-the-art by 7.5\% in mAP$_{0.5:0.95}$ on the VisDrone2019 dataset.

<div align="center">
<img src="network.png"/>
</div>

## Installation
Required environments:

-   Linux
-   Python 3.6+
-   PyTorch 1.3+
-   CUDA 9.2+
-   GCC 5+
-   Transformers 4.45.0+
-   [MMCV](https://mmcv.readthedocs.io/en/latest/#installation)
-   [cocoapi-aitod](https://github.com/jwwangchn/cocoapi-aitod)

Install:

Note that this repository is based on the [MMDetection](https://github.com/open-mmlab/mmdetection). Assume that your environment has satisfied the above requirements, please follow the following steps for installation.

    git clone https://github.com/cszzshi/VLM4RSDet.git
    cd VLM4RSDet
    pip install -v -e .

Verify the installation:

To verify whether MMDetection is installed correctly, we provide some sample codes to run an inference demo.

**Step 1.** We need to download config and checkpoint files.

    mim download mmdet --config rtmdet_tiny_8xb32-300e_coco --dest .
  
  **Step 2.** Verify the inference demo.
  
    python demo/image_demo.py demo/demo.jpg rtmdet_tiny_8xb32-300e_coco.py --weights rtmdet_tiny_8xb32-300e_coco_20220902_112414-78e30dcc.pth --device cpu

You will see a new image `demo.jpg` on your `./outputs/vis` folder, where bounding boxes are plotted on cars, benches, etc.

## Get Started

Prepare the dataset:

VisDrone2019 dataset
 - trainset (1.44 GB): [Baidu Yun](https://pan.baidu.com/s/1K-JtLnlHw98UuBDrYJvw3A) | [Google Drive](https://drive.google.com/file/d/1a2oHjcEcwXP8oUF95qiwrqzACb2YlUhn/view?usp=sharing)
 - valset (0.07 GB): [Baidu Yun](https://pan.baidu.com/s/1jdK_dAxRJeF2Xi50IoML1g) | [Google Drive](https://drive.google.com/file/d/1bxK5zgLn0_L8x276eKkuYA_FzwCIjb59/view?usp=sharing)

Train and test:

**Step 1.** Train the model using single GPU.

    python tools/train.py configs/VLM4RSDet/visdrone/faster-rcnn_r50_fpn_1x_VLM4RSDet_visdrone.py

**Step 2.** Test the trained weight using single GPU.

    python tools/test.py configs/VLM4RSDet/visdrone/faster-rcnn_r50_fpn_1x_VLM4RSDet_visdrone.py work_dirs/visdrone/faster-rcnn_r50_fpn_1x_VLM4RSDet_visdrone/epoch_12.pth

## Citation

Welcome to cite this project in your research.

```
@InProceedings{,
    author={Shi, Shuohao and Fang, Qiang and Xu, Xin},
    title={VLM4RSDet: Collaborative Optimization with Vision-Language Model for Enhancing Remote Sensing Object Detection},
    booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    year={2026},
    pages={-}
}
```
