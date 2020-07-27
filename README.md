# Window Detection in Facades Using Heatmaps Fusion
Official implementation of our paper [Window Detection in Facades Using Heatmap Fusion](http://jcst.ict.ac.cn/EN/10.1007/s11390-020-0253-4)

# Introduction
Window detection is a key component in many graphics and vision applications related to 3D city modeling and scene visualization. We present a novel approach for learning to recognize windows in a colored facade image. Rather than predicting bounding boxes or performing facade segmentation, our system locates keypoints of windows, and learns keypoint relationships to group them together into windows. A further module  provides extra recognizable information at the window center. Locations and relationships of keypoints are encoded in different types of heatmaps, which are learned in an end-to-end network. 
We have also constructed a facade dataset with 3418 annotated images  to facilitate  research in this field. It has richly varying facade structure, occlusion, lighting conditions, and angle of view.
On our dataset, our method achieves  precision of 91.4\% and  recall of 91.0\% under 50\% IoU. We also make a quantitative comparison with state-of-the-art methods to verify the utility of our proposed method. 
Applications based on our window detector are also demonstrated, such as window blending.

![image](https://github.com/lck1201/win_det_heatmaps/raw/master/docs/framework.jpg)

# Preparation
**Environment**

Please Install PyTorch following the guideline in the [official webite](https://pytorch.org/). In addition, you have to install other necessary dependencies.
```bash
pip3 install -r requirements.txt
```

**Dataset**

Coming soon...


**Model**

You can use our trained models from [BaiduYun](https://pan.baidu.com/s/1ipAp5Tg4ZsmxOvHCD_9IlQ)(code: 0x97). ResNet18, MobileNetV2, ShuffleNetV2 and corresponding configuration files are provided. All the configurations are written in \*.yaml files and config_pytorch.py, and you can change it up to your own needs.

# Usage
**Train**
```bash 
python train.py --cfg /path/to/yaml/config \
    --data /path/to/data/root \
    --out /path/to/output/root
```

**Test**
```bash 
python test.py --cfg /path/to/yaml/config --model /path/to/model \
    --data /path/to/data/root \
    --out /path/to/output/root
```


**Inference**
```bash
python infer.py --cfg /path/to/yaml/config \
                --model /path/to/model \
                --infer /path/to/image/directory
```

# Examples
<div align="center">
    <img src="https://github.com/lck1201/win_det_heatmaps/raw/master/docs/example1.jpg" width="850">
</div>

# Applications
**Facade Unification**

We have developed a computational workflow for window texture blending based on our window detection method. Based on our technique, graphics designer can easily manipulate facade photos to create ideal building textures, while removing windows which are unsatisfactory  due to their open or closed status, lighting conditions and occlusion,  replacing them with the selected unified window texture.
<div align="center">
    <img src="https://github.com/lck1201/win_det_heatmaps/raw/master/docs/textureBlendingApp.jpg" width="650">
</div>

**Facade Beautification**

Applying the above workflow, image beautification can be also performed to generate visually pleasant results with mixed features. 
<div align="center">
    <img src="https://github.com/lck1201/win_det_heatmaps/raw/master/docs/facade_beautification.jpg" width="550">
</div>

**Facade Analytics**

As our method can efficiently locate windows in urban facade images, it is of use for automatically analyzing semantic structure and extracting numerical information. With additional simple steps, it is easy to determine the windows in a single row or  column. Furthermore, it can be adopted to predict building layers and symmetric feature lines.
<div align="center">
    <img src="https://github.com/lck1201/win_det_heatmaps/raw/master/docs/facade_analytics.jpg" width="650">
</div>

# Citation
If you find our code/dataset/models/paper helpful in your research, please cite with:
> @article{Chuan-Kang Li:900, <br/>
author = {Chuan-Kang Li, Hong-Xin Zhang, Jia-Xin Liu, Yuan-Qing Zhang, Shan-Chen Zou, Yu-Tong Fang},<br/>
title = {Window Detection in Facades Using Heatmap Fusion},<br/>
publisher = {Journal of Computer Science and Technology},<br/>
year = {2020},<br/>
journal = {Journal of Computer Science and Technology},<br/>
volume = {35},<br/>
number = {4},<br/>
eid = {900},<br/>
numpages = {12},<br/>
pages = {900},<br/>
keywords = {facade parsing;window detection;keypoint localization},<br/>
url = {http://jcst.ict.ac.cn/EN/abstract/article_2660.shtml},<br/>
doi = {10.1007/s11390-020-0253-4}<br/>
}    


 
# Acknowledgement
The major contributors of this repository include [Chuankang Li](https://github.com/lck1201), [Yuanqing Zhang](https://github.com/yuanqing-zhang), [Shanchen Zou](https://github.com/Generior), and [Hongxin Zhang](https://person.zju.edu.cn/zhx).

