# DiverseAR+ Dataset
This repository introduces **DiverseAR+**, a dataset of 1405 AR images collected from various platforms and scenarios. 

# Dataset
The samples of the DiverseAR+ dataset can be found in the dataset folder. The full DiverseAR+ dataset can be downloaded from ()[]. The dataset follows the hierarchical file structure shown below:
```
dataset
└───diverseAR_images
│   └───image_1.png
│   ...
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
```

_Creation:_ The DiverseAR+ dataset comprises 1,405 AR images along with the associated metadata. Figure 1 presents representative AR examples from the DiverseAR+, illustrating a range of quality levels across all visual factors. We collected the samples from diverse sources and environments using commercial and custom-developed AR applications. Specifically, we captured 320 samples by Apple Vision Pro and 826 samples by Android phones (Galaxy S25 and Pixel 7) across various settings, including bedrooms, living rooms, study rooms, kitchens, and simulated museum environments, in which virtual objects were overlaid onto static museum images; 135 samples by HoloLens 2 in medical settings using virtual anatomical models; and 124 samples from external sources (29 public websites, 53 commercial apps, 42 prior studies). In addition, we recorded complementary metadata, including depth information (for Android devices and HoloLens 2) and the pose data of the camera, headset, virtual object, and virtual light in the scene to support further analysis. 

_Details:_ Each image features a single virtual object selected from a total of 29 classes. These span a range of domains including: medical anatomies of a human body (e.g., eye, brain, bone, liver, heart), dynamic, user-manipulable objects (e.g., basketball, football, glove), and stationary objects (e.g., chair, can, box, table, etc.). The dataset captures a diverse range of visual quality statuses across 3 factors, recognized as key dimensions of photorealistic coherence and user safety in AR: **shadow realism, floating plausibility, intersection coherence**.

<p align="center"><img width="600" alt="Representative AR examples from the DiverseAR+ dataset illustrating various quality levels across 3 visual factors." src="https://github.com/ARResearcher/ARQA/blob/main/images/DiverseAR+_samples.png"></p>
<p align="center">Figure 1. Representative AR examples from the DiverseAR+ dataset illustrating various quality levels across 3 visual factors: (1) Shadow realism: Virtual basket with fair shadow strength, rendered with opposite (poor), slightly different (slightly degraded), or same (good) direction as the real shadow; (2) Intersection coherence: Virtual toy dinosaur clearly intersecting a real bottle (poor), slightly sinking into the board (slightly degraded), or correctly positioned on the table (good); (3) Floating plausibility: Virtual can that appears obviously detached (poor), slightly elevated (slightly degraded), or properly seated (good).</p> 
