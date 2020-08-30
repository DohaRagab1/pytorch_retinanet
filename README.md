# pytorch_retinanet
A simple implementations of `Retinanet` for `object detection` as described in the paper [Focal Loss for Dense Object Detection](https://arxiv.org/abs/1708.02002).
- This project uses [`PyTorch`](https://pytorch.org/). 
- For training, it is recommended to use [`PyTorchLightning`](https://github.com/PyTorchLightning/pytorch-lightning). Ready to use scripts will be utilizing PyTorchLightning. 
- I also plan to use [`Hydra`](https://github.com/facebookresearch/hydra) to maintain the config files and [`Albumentations`](https://github.com/albumentations-team/albumentations) for image transformations/augmentations.

## TODO: 
- [x] Create `Anchor Generator`.
- [x] Create `ResNet` based `BackBone Model`.
- [x] Create `FeaturePyramid` architecture as described in https://arxiv.org/abs/1612.03144.
- [x] [Focal Loss](https://arxiv.org/abs/1708.02002) & `Regeression` and `Classification` Head for `Retinanet`.
- [x] Assemble Retinanet Using `BackBone` => `FeaturePyramid` => `AnchorGenerator` => `Regeression` & `Classification` Head.
- [x] Decode `Retinanet Predictions`. 
- [x] Test model training on toy dataset.
  - [x] Check `Training`. [Failing: in losses.py:`cuda error`]
  - [x] Fix `cuda` errors in losses.py
  - [x] Evaluation using `COCO API`. [scripts taken from: https://github.com/PyTorchLightning/wheat]
  - [x] Fix `nan` losses during training.
- [ ] Train on Pascal VOC 2007.
  - [x] Fix augmentation pipeline
  - [x] Log wandb & TensorBoard
  - [x] Evaluation using `COCO API`.
  - [ ] Final `COCO` mAP: 
- [ ] Ready made easy to use scripts for `training` & `inference`.
- [ ] Train on COCO dataset. (Not sure if I have the resources)

## Updates
- Started Training on [The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) ran to many errors. 😭
- Fixed the errors was able to train on the [The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/). Reached a mAP of 0.5 before Colab resources ran out. I plan to update the notebooks in the `references` soon.
- 27 August 2020:
  - Started training on [Pascal VOC 2007](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/index.html).
  - Ran into errors mainly due to albumentations removing boxes.
  - Fixed my image transformation pipeline.
  - Using PyTorchLightning Trainer to automate my training process: it's just awesome. 😎 
  - Trainining is going on smoothly. [notebook](https://github.com/benihime91/pytorch_retinanet/blob/master/references/train_pascal_2007.ipynb).
