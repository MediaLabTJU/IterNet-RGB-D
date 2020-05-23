## Learning to Reconstruct and Understand Indoor Scenes from Sparse Views
by Jingyu Yang, Ji Xu, Kun Li, Yu-Kun Lai, Huanjing Yue, Jianzhi Lu, Hao Wu and Yebin Liu.

### Introdution
This code is related to our paper "[Learning to Reconstruct and Understand Indoor Scenes from Sparse Views](https://arxiv.org/abs/1906.07892)" accepted by TIP2020.

The source code is build for *IterNet*, which is an itertive joint optimiation method for depth estimation and semantic segmntation proposed by our paper. For installtion, please make sure to install [caffe](https://github.com/BVLC/caffe) environment.

In addition, we proposed *IterNet RGB-D* dataset, including photorealistic high-resolution RGB images, accurate depth maps,
and pixel-level semantic labels for thousands of complex
layouts.

### Dataset
#### 1. OverView
Our proposed dataset is a synthetic dataset and is generted by a third-party platform which includes various real-life house styles, real prototype rooms designed by professional designers, and detailed model materials. Besides, we also implement high-quality photorealistic rendring. Compared to traditional rendering, we adopt the method of image splitting and recombination to achieve distributed rendering. 

Table 1 compares various publicly available 2.5/3D indoor datasets with our IterNet RGB-D dataset. Our dataset provides a total of 12,856 photorealistic images for thousands of layouts, and has a higher image resolution: 1280 × 960 and 1280 × 720, covering more indoor scenes. Moreover, our dataset provides absolute depth maps and pixel-level semantic segmentation that are more precise and accurate. Compared with other datasets, the indoor scenes covered by our dataset are more general and more complex.

 <table>
        <tr>
            <th>Dataset</th>
            <th>NYUv2</th>
            <th>SUN RGB-D</th>
            <th>Building Paraser</th>
            <th>Matterport 3D</th>
            <th>ScanNet</th>
            <th>SUNCG</th>
            <th>SceneNet RRG-D</th>
            <th>IterNet RGB-D</th>
        </tr>
        <tr>
            <th>Year</th>
            <th>2012</th>
            <th>2015</th>
            <th>2017</th>
            <th>2017</th>
            <th>2017</th>
            <th>2017</th>
            <th>2016</th>
            <th>2019</th>
        </tr>
        <tr>
            <th>Type</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Synthetic</th>
            <th>Synthetic</th>
            <th>Synthetic</th>
        </tr>
        <tr>
            <th>Image/Scans</th>
            <th>1449</th>
            <th>10k</th>
            <th>70k</th>
            <th>194k</th>
            <th>1513</th>
            <th>130k</th>
            <th>5M</th>
            <th>12856</th>
        </tr>
        <tr>
            <th>Layouts</th>
            <th>464</th>
            <th>-</th>
            <th>270</th>
            <th>90</th>
            <th>1513</th>
            <th>45622</th>
            <th>57</th>
            <th>3214</th>
        </tr>
        <tr>
            <th>Object Classes</th>
            <th>894</th>
            <th>800</th>
            <th>13</th>
            <th>40</th>
            <th>>=50</th>
            <th>84</th>
            <th>255</th>
            <th>333</th>
        </tr>
        <tr>
            <th>RGB</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>❎</th>
            <th>❎</th>
            <th>✅</th>
            <th>✅</th>
        </tr>
        <tr>
            <th>Depth</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>❎</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
        </tr>
        <tr>
            <th>Semantic Label</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
            <th>❎</th>
            <th>✅</th>
            <th>✅</th>
            <th>✅</th>
        </tr>
        <tr>
            <th>RGB Texturing</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Real</th>
            <th>Not Photorealistic</th>
            <th>Photorealistic</th>
            <th>Photorealistic</th>
        </tr>
        <tr>
            <th>Image Resolution</th>
            <th>640X480</th>
            <th>640X480</th>
            <th>1080X1080</th>
            <th>1280X1024</th>
            <th>640X480</th>
            <th>640X480</th>
            <th>320X240</th>
            <th>1280×960;1280×720</th>
        </tr>
        <caption>Table 1. Comparison between various indoor datasets.</caption>
    </table>

Figure 1 shows some examples of different scenarios in our dataset.  It can be seen that our dataset contains more complex indoor layouts, richer textures, colorful and realistic lightings, and higher resolution images, which are more photorealistic and closer to real-world images.

![Figure 1](resource/dataset.png)

#### 2. Details
Each sample of the dataset is composed of 4 parts. The picture in jpeg format represents RGB image, and the "zDepth" suffix is the depth image. The remaining picture suffixed with "VRayObjectID" and a "txt" file together to express semantic information of the scene. Each combination of RGB corresponds to a material id, which corresponds to an object category.

We divide the dataset into two parts for everyone to use. The first part of the data is artificially filtered, and a small amount of scene data is removed (when the window is rendered, it is rendered outdoors). The second part of the data is not processed manually, and the scene is more abundant.

### Code
Figure 2 shows our proposed *IterNet* architecture, which is uesd for itertive joint optimiation for depth estimation and semantic segmntation. More Deatails can be found in the paper.

【传图片。。。】


### Citation
If our work is useful for your research, please consider citing:

```
@article{Yang2019Learning,
  title={Learning to Reconstruct and Understand Indoor Scenes from Sparse Views},
  author={Yang, Jingyu and Xu, Ji and Li, Kun and Lai, Yu-Kun and Yue, Huanjing and Lu, Jianzhi and Wu, Hao and Liu, Yebin},
  year={2019},
}
```

### Question
Please contact Prof. Kun Li at lik@tju.edu.cn  if you have any questions.
