# ARQA Dataset
This repository accompanies the paper "_Bridging Human Perception and Automated Evaluation: Vision-Language Model-Based Visual Quality Assessment of AR-Generated Scenes_", submitted to ISMAR 2025. It introduces **ARQA**, a dataset of 1107 background and AR image pairs collected from 4 AR applications (Apple Vision Pro, HoloLens 2 and 2 Android phones) specifically created for this project. 

# Dataset
The full ARQA dataset can be downloaded here: [https://](https://) The dataset follows the hierarchical file structure shown below:
```
images
└───android
│   │
│   └───android-xxxxxx.png
│   ...
└───hl
│   │
│   └───IMG_xxxx.jpg
│   ...
└───avp
│   │
│   └───IMG_xxxx.png
│   ...
```

_Creation:_ To evaluate the xxx capabilities of VLMs, we curated the ARQA dataset, specifically designed to capture a broad spectrum of xxx. The dataset consists of **1107 background and AR image pairs** collected from diverse sources and environments. It includes xx images captured using a custom-developed Apple Vision Pro AR application in laboratory and kitchen environments, and xx images collected from a custom-developed Android AR application in bedroom and dining room environments. Additionally, 42 images were created in-house to explore AR-specific research topics, such as AR applications in surgical guidance. This comprehensive collection ensures the ARQA dataset supports robust analysis of xxx. 

_Details:_ The ARQA dataset encompasses a wide spectrum of AR scenarios, showcasing diverse characteristics of both virtual and real-world content. Table below summarizes the key characteristics represented in the dataset, while Figure below illustrates representative examples of these characteristics. The dataset includes single or multiple instances of identical and varied real and virtual objects across various AR images. These objects span numerous classes, including **toys, food, shoes, plants, laptops, containers, and more**.

<p align="center"><img width="1000" alt="Key characteristics of the virtual and real objects in the ARQA dataset." src="https://github.com/.png"></p>

# Small-scale datasets

# Rule-based method mapping function and parameters



<p align="center"><img width="407" alt="Examples of key characteristics of the virtual and real objects in the ARQA dataset." src="https://github.com/.png"></p>
<p align="center">Figure 1. Examples of key characteristics of the virtual and real objects in the ARQA dataset.</p> 


The three AR scene difficulty levels are labeled in the labeled_images.csv file.
