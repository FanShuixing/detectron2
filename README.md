
## Detectron2

### Installation
```angular2
pytorch1.3 
pip install 'git+https://github.com/facebookresearch/fvcore'
pip install cython; pip install 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
GCC>=4.9
```

### Train
```angular2
python tools/train_net.py \
	--config-file configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml \
    SOLVER.IMS_PER_BATCH 2 SOLVER.BASE_LR 0.0025
```

### Predict
```angular2
#将demo.py的代码修改，从而通过读取test.txt文件来生成test.txt目录下所有图片的预测效果图，并输出预测的json文件
python demo/demo.py --config-file /output/config.yaml  --input test.txt --output test_img/  --opts MODEL.WEIGHTS /output/model_final.pth 
```