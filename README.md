<!--
 * @Author: your name
 * @Date: 2022-02-11 20:05:32
 * @LastEditTime: 2022-02-12 15:22:45
 * @LastEditors: Irving.Gao
 * @Description: 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
 * @FilePath: /DDOD/README.md
-->

# Disentangle Your Dense Object Detector


This repo contains the supported code and configuration files to reproduce object detection results of [Disentangle Your Dense Object Detector](https://arxiv.org/abs/2107.02963). It is based on [mmdetection](https://github.com/open-mmlab/mmdetection).

## Results and Models

| Model | Backbone | Lr Schd | box mAP | AP50 | AP75 | APs | APm | APl |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |:---: |
| ATSS(IoU) | ResNet50 | 1x | 39.4 | 56.6 | 42.6 | 23.9 | 42.5 | 49.6 |
| DDOD | ResNet50 | 1x | 41.6 | 59.9 | 45.2 | 23.9 | 44.9 | 54.4 |
| DDOD-FCOS | ResNet50 | 1x | 41.6 | 59.9 | 45.3 | 24.0 | 44.6 | 54.8 |

## Usage

### Installation

Please refer to [get_started.md](https://github.com/open-mmlab/mmdetection/blob/master/docs/get_started.md) for installation and dataset preparation.

Or you can also fllow the simple steps:

```bash
git clone https://github.com/Irvingao/DDOD.git
cd DDOD
pip install -r requirements/build.txt
pip install -v -e .  
```


### Inference
```
# multi-gpu testing
tools/dist_test.sh coco_cfg/ddod_r50_1x.py <DET_CHECKPOINT_FILE> 8 --eval bbox
```

### Training

To train a detector with pre-trained models, run:
```
# single-gpu training
python tools/train.py coco_cfg/ddod_r50_1x.py
```

```
# multi-gpu training
tools/dist_train.sh coco_cfg/ddod_r50_1x.py 8
```

## Citing DDOD
```
@misc{chen2021disentangle,
      title={Disentangle Your Dense Object Detector}, 
      author={Zehui Chen and Chenhongyi Yang and Qiaofei Li and Feng Zhao and Zhengjun Zha and Feng Wu},
      year={2021},
      eprint={2107.02963},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```