# ARQA Dataset
This repository accompanies the paper "_Bridging Human Perception and Automated Evaluation: Vision-Language Model-Based Visual Quality Assessment of AR-Generated Scenes_", submitted to ISMAR 2025. It introduces **ARQA**, a dataset of 1107 background and AR image pairs collected from 4 AR applications (Apple Vision Pro, HoloLens 2 and 2 Android phones) specifically created for this project. 

# Dataset
The samples of the ARQA dataset can be found in the ARQA_dataset folder. The full ARQA dataset will be released by August 2025. The dataset follows the hierarchical file structure shown below:
```
ARQA_dataset
└───android
│   │
│   └───android_Basketball
│   │   └───android_Basketball_1_raw.png
│   │   └───android_Basketball_1_ar.png
│   │   └───android_Basketball_1_depth.png
│   │   └───android_Basketball_1_RenderingSettings.json
│   ...
└───hl
│   │
│   └───hl_heart
│   │   └───hl_heart_1_raw.jpg
│   │   └───hl_heart_1_ar.jpg
│   │   └───hl_heart_1_depth.jpg
│   │   └───hl_heart_1_pose.csv
│   ...
└───AVP
│   │
│   └───AVP_balloon
│   │   └───AVP_balloon_1_raw.png
│   │   └───AVP_balloon_1_ar.png
│   │   ...
│   │   └───AVP_balloon_rendering_settings.csv
│   │   ...
│   ...
```

_Creation:_ The ARQA dataset comprises 1,107 background and AR image pairs along with the associated metadata. Figure 1 presents representative AR examples from the ARQA, illustrating a range of quality levels across all visual factors. We collected the image pair samples from diverse sources and environments using a custom-developed AR application on each device. Specifically, we captured: 297 samples by the AVP in research lab and reading room environments; 675 samples by two Android phones, Samsung Galaxy S25 and Google Pixel 7 across various settings, including bedrooms, living rooms, study rooms, kitchens, and simulated museum environments, in which virtual objects were overlaid onto static museum images; 135 samples by HoloLens 2 in medical settings using virtual anatomical models. In addition, we recorded complementary metadata, including depth information (for Android devices and HoloLens 2) and the pose data of the camera, headset, virtual object, and virtual light in the scene to support further analysis. 

_Details:_ Each image features a single virtual object selected from a total of 29 classes. These span a range of domains including: medical anatomies of a human body (e.g., eye, brain, bone, liver, heart), dynamic, user-manipulable objects (e.g., basketball, football, glove), and stationary objects (e.g., chair, can, box, table, etc.). The dataset captures a diverse range of visual quality statuses across seven factors, recognized as key dimensions of photorealistic coherence and user safety in AR: **shadow realism, light direction coherence, light intensity coherence, size appropriateness, floating plausibility, intersection coherence, occlusion appropriateness**.

<p align="center"><img width="1000" alt="Representative AR examples from the ARQA dataset illustrating various quality levels across 7 visual factors." src="https://github.com/ARResearcher/ARQA/blob/main/images/ARQA_samples.png"></p>
<p align="center">Figure 1. Representative AR examples from the ARQA dataset illustrating various quality levels across 7 visual factors: (1) Shadow reailsm: Virtual basket with fair shadow strength, rendered with opposite (poor), slightly different (slightly degraded), or same (good) direction as the real shadow; (2) Light direction coherence: Virtual table illuminated from an opposite (poor), slightly different (slightly degraded), or consistent (good) direction compared to real light; (3) Light intensity coherence: Virtual eye with very dark (poor), bright but detail-obscuring (slightly degraded), or clear (good) light intensity; (4) Intersection coherence: Virtual toy dinosaur clearly intersecting a real bottle (poor), slightly sinking into the board (slightly degraded), or correctly positioned on the table (good); (5) Floating plausibility: Virtual can that appears obviously detached (poor), slightly elevated (slightly degraded), or properly seated (good); (6) Size appropriateness: Virtual car depicted as obviously small (poor), slightly small (slightly degraded), or normal-sized (good); (7) occlusion appropriateness: Virtual balloon that fully (poor), partially (slightly degraded), or does not block (good) the warning sign on the wall.</p> 

The 8 AR quality human labels are in the labeled_images.csv file.

# Small-scale datasets

_Creation:_ We curated small-scale datasets (released alongside the ARQA dataset) corresponding to recognized dimensions of AR visual realism: shadow realism, light source direction coherence, light intensity coherence, intersection coherence, floating plausibility, and size appropriateness. Each dataset comprises AR images, captured using AVP and Android smartphones, and randomly selected VR images from VIDTI, a widely used VR image dataset, covering varying degrees of these factors. Figure 2 shows examples of those images for each visual factor.

<p align="center"><img width="407" alt="Example images from the small-scale datasets illustrating various factors." src="https://github.com/ARResearcher/ARQA/blob/main/images/Motivation_dataset.png"></p>
<p align="center">Figure 2. Example images from the small-scale datasets illustrating various factors: (a) Shadow realism: a virtual butterfly toy with a ground shadow placed on the floor; (b) Light Direction coherence: a VR scene where the light comes from behind; (c) Light Intensity coherence: an overly bright can on a table; (d) Intersection coherence: a virtual chair partially intersecting with a table; (e) Floating plausibility: a virtual basketball suspended above a table; and (f) Size appropriateness: an oversized virtual apple on a table.</p> 

# Rule-based method mapping function and parameters

