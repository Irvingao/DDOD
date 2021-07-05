# Disentangle Your Dense Object Detector

This repo contains the supported code and configuration files to reproduce object detection results of [DDOD](https://arxiv.org/pdf/xxxxxx.pdf). It is based on [mmdetection](https://github.com/open-mmlab/mmdetection).

## Results and Models

| Model | Backbone | Lr Schd | box mAP | AP50 | AP75 | APs | APm | APl |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |:---: |
| ATSS(IoU) | ResNet50 | 1x | 39.4 | 56.6 | 42.6 | 23.9 | 42.5 | 49.6 |
| DDOD | ResNet50 | 1x | 41.6 | 59.9 | 45.2 | 23.9 | 44.9 | 54.4 |

## Usage

### Installation

Please refer to [get_started.md](https://github.com/open-mmlab/mmdetection/blob/master/docs/get_started.md) for installation and dataset preparation.

### Inference
```
# multi-gpu testing
tools/dist_test.sh coco_cfg/ddod_r50_1x.py <DET_CHECKPOINT_FILE> 8 --eval bbox
```

### Training

To train a detector with pre-trained models, run:
```
# multi-gpu training
tools/dist_train.sh coco_cfg/ddod_r50_1x.py 8
```

## Citing DDOD
```
@article{xxxxxx,
  title={Disentangle Your Dense Object Detector},
  author={Chen, Zehui and Yang, Chenhongyi and Li, Qiaofei and Zhao, Feng and Zha, Zhengjun and Wu, Feng},
  journal={arXiv preprint arXiv:xxxxxx},
  year={2021}
}
```