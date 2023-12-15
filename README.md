
## Project structure
```
Synthetic_Image_Object_Detection
├─ .gitignore
├─ archive  # implementation pytorch 
├─ data  
│  ├─ raw
│  │  └─ raw data
│  └─ submission
├─ models
│  └─ model file
├─ mmdetection
│  ├─ configs  
│  │  ├─ _base_  
│  │  └─ ME  # model config
│  │      └─ model config file.py
│  └─ mmdet
├─ inference.py # Test Inference
├─ grad_cam.py  # GradCam
└─ README.md
```
## Getting Started
`Python 3.8.10` `mmdetection 2`
```
git clone https://github.com/jjuhyeok/PythonBasedDeepLearning_Final_Project.git

python -m pip install --upgrade pip
python -m pip install -r requirements.txt

cd mmdetection
python .\tools\train.py .\configs\{config_file.py}
python .\tools\test.py '{config_file_path}' '{model_result_path}' --format-only --out '{result_path}'
```
## Data
[Dataset Link](https://)  


## Experiment
기본 적용된 증강 기법은 Resize, Flip, Normalize입니다.   
실험에는 Faster R-CNN, EfficientDet, Swin Transformer, Libra R-CNN, 그리고 YOLO가 사용되었습니다.  
다른 실험들은 "finished_experiments" 폴더에서 확인할 수 있습니다. FINAL은 Cascade R-CNN 모델이 사용되었습니다.  

| Model         | Backbone | Depth | Augmentation                                      |  mAp |
|---------------|----------|-------|---------------------------------------------------|------|
| Cascade R-CNN | SwinT    | -     | Mixup, Cutout                                     | 0.89 |
| Libra R-CNN   | Resnest  | 200   | Mixup, Cutout, AutoAugment, PhotoMetricDistortion | 0.89 |
| Faster R-CNN  | ResNeXt  | 101   | Mixup                                             | 0.91 |
| Faster R-CNN  | ResNeSt  | 200   | Mixup                                             | 0.93 |
| Faster R-CNN  | ResNeSt  | 101   | Mixup, Cutout                                     | 0.95 |
| Cascade R-CNN | ResNeSt  | 200   | Mixup, Cutout, AutoAugment, PhotoMetricDistortion | 0.98 |
| ...           | ...      | ...   | ...                                               | ...  |


## Result
mAP `0.`
 
## Development Environment
```
OS: Window11
CPU: Intel i9-11900K
RAM: 128GB
GPU: NVIDIA GeFocrce A100
```
