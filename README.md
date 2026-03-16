# VLM4RSDet
This is the official implementation of the paper "VLM4RSDet: Collaborative Optimization with Vision-Language Model for Enhancing Remote Sensing Object Detection".
## Introduction
VLM4RSDet is a novel collaborative training framework that leverages vision-language models to enhance traditional closed-set remote sensing object detectors without introducing any additional deployment overhead.

**Abstract**: Closed-set object detection in remote sensing imagery has made significant progress, but achieving high detection accuracy remains challenging. Vision-Language Models (VLMs), which possess rich prior knowledge, offer a promising solution to this challenge. However, most existing VLMs are designed for open-vocabulary tasks and exhibit inherent limitations when directly applied to closed-set scenarios, such as notable accuracy degradation and high deployment costs. To address these issues, we propose VLM4RSDet, a novel collaborative training framework that leverages vision-language model to enhance the performance of conventional closed-set remote sensing object detectors. Notably, during inference, VLM4RSDet only retains the standard object detection architecture, thus avoiding any additional deployment overhead. Furthermore, we introduce a Global–Local Cross-Attention (GLCA) module and a Learnable Hierarchical Prediction Strategy (LHPS) to further improve collaborative training performance. Extensive experiments on five benchmark datasets demonstrate the effectiveness and robustness of our approach. In particular, our method outperforms the state-of-the-art by 7.5\% in mAP$_{0.5:0.95}$ on the VisDrone2019 dataset.

<div align="center">
<img src="network.png"/>
</div>

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
