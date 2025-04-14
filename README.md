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

<p align="center"><img width="1000" alt="Representative AR examples from the ARQA dataset illustrating various quality levels across 7 visual factors: (1) Shadow reailsm: Virtual basket with fair shadow strength, rendered with opposite (poor), slightly different (slightly degraded), or same (good) direction as the real shadow; (2) Light direction coherence: Virtual table illuminated from an opposite (poor), slightly different (slightly degraded), or consistent (good) direction compared to real light; (3) Light intensity coherence: Virtual eye with very dark (poor), bright but detail-obscuring (slightly degraded), or clear (good) light intensity; (4) Intersection coherence: Virtual toy dinosaur clearly intersecting a real bottle (poor), slightly sinking into the board (slightly degraded), or correctly positioned on the table (good); (5) Floating plausibility: Virtual can that appears obviously detached (poor), slightly elevated (slightly degraded), or properly seated (good); (6) Size appropriateness: Virtual car depicted as obviously small (poor), slightly small (slightly degraded), or normal-sized (good); (7) occlusion appropriateness: Virtual balloon that fully (poor), partially (slightly degraded), or does not block (good) the warning sign on the wall." src="https://github.com/.png"></p>

# Small-scale datasets

# Rule-based method mapping function and parameters



<p align="center"><img width="407" alt="Example images from the small-scale datasets illustrating various factors: (a) Shadow realism: a virtual butterfly toy with a ground shadow placed on the floor; (b) Light Direction coherence: a VR scene where the light comes from behind; (c) Light Intensity coherence: an overly bright can on a table; (d) Intersection coherence: a virtual chair partially intersecting with a table; (e) Floating plausibility: a virtual basketball suspended above a table; and (f) Size appropriateness: an oversized virtual apple on a table." src="https://github.com/ARResearcher/ARQA/blob/main/images/Motivation_dataset.png"></p>
<p align="center">Figure 2. Example images from the small-scale datasets illustrating various factors: (a) Shadow realism: a virtual butterfly toy with a ground shadow placed on the floor; (b) Light Direction coherence: a VR scene where the light comes from behind; (c) Light Intensity coherence: an overly bright can on a table; (d) Intersection coherence: a virtual chair partially intersecting with a table; (e) Floating plausibility: a virtual basketball suspended above a table; and (f) Size appropriateness: an oversized virtual apple on a table.</p> 


The three AR scene difficulty levels are labeled in the labeled_images.csv file.
