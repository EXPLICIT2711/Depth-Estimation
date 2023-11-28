# Depth-Estimation

## Training with DenseNet 169 encoder
* Train from scratch: 
```
python train.py --data nyu --bs 5 --full 
```

## Training with DenseNet 121 encoder
```
python train.py --data nyu --bs 5 --full --dnetVersion small
```

## Training with ResNet50 encoder
```
python train.py --data nyu --bs 5 --name resnet50_nyu --full --resnet
```

## Evaluation
* Download, but don't extract, the ground truth test data from [here](https://s3-eu-west-1.amazonaws.com/densedepth/nyu_test.zip) (1.4 GB). The call evaluate.py with your model checkpoint

```
python evaluate.py --model ./models/1557483797-n10138-e20-bs5-lr0.0001-densedepth_nyu/weights.06-0.12.h5
```

## Visualizations on images and videos outside the NYU Depth V2 data

### Visualization on images outside the test set - displays image + predicted depth map
Put the images in my_examples folder
```
python test.py --model <model-checkpoint-path>
```

### Visualization on videos outside the test set - displays image + predicted depth map
Pass the checkpoint to the model. The results are stored in the folder called image_results
```
python test_video.py --model <model-checkpoint-path> --input <path-to-video>
```

## Reference
Corresponding paper to cite:
```
@article{Alhashim2018,
  author    = {Ibraheem Alhashim and Peter Wonka},
  title     = {High Quality Monocular Depth Estimation via Transfer Learning},
  journal   = {arXiv e-prints},
  volume    = {abs/1812.11941},
  year      = {2018},
  url       = {https://arxiv.org/abs/1812.11941},
  eid       = {arXiv:1812.11941},
  eprint    = {1812.11941}
}
```
