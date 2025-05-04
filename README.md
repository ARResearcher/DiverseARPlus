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
<p align="center">Figure 1. Representative AR examples from the ARQA dataset illustrating various quality levels across 7 visual factors: (1) Shadow realism: Virtual basket with fair shadow strength, rendered with opposite (poor), slightly different (slightly degraded), or same (good) direction as the real shadow; (2) Light direction coherence: Virtual table illuminated from an opposite (poor), slightly different (slightly degraded), or consistent (good) direction compared to real light; (3) Light intensity coherence: Virtual eye with very dark (poor), bright but detail-obscuring (slightly degraded), or clear (good) light intensity; (4) Intersection coherence: Virtual toy dinosaur clearly intersecting a real bottle (poor), slightly sinking into the board (slightly degraded), or correctly positioned on the table (good); (5) Floating plausibility: Virtual can that appears obviously detached (poor), slightly elevated (slightly degraded), or properly seated (good); (6) Size appropriateness: Virtual car depicted as obviously small (poor), slightly small (slightly degraded), or normal-sized (good); (7) Occlusion appropriateness: Virtual balloon that fully (poor), partially (slightly degraded), or does not block (good) the warning sign on the wall.</p> 

The 8 AR quality human labels are in the labeled_images.csv file.

# Small-scale datasets

_Creation:_ We curated small-scale datasets (released alongside the ARQA dataset) corresponding to recognized dimensions of AR visual realism: shadow realism, light source direction coherence, light intensity coherence, intersection coherence, floating plausibility, and size appropriateness. Each dataset comprises AR images, captured using AVP and Android smartphones, and randomly selected VR images from VIDTI, a widely used VR image dataset, covering varying degrees of these factors. Figure 2 shows examples of those images for each visual factor.

<p align="center"><img width="407" alt="Example images from the small-scale datasets illustrating various factors." src="https://github.com/ARResearcher/ARQA/blob/main/images/Motivation_dataset.png"></p>
<p align="center">Figure 2. Example images from the small-scale datasets illustrating various factors: (a) Shadow realism: a virtual butterfly toy with a ground shadow placed on the floor; (b) Light Direction coherence: a VR scene where the light comes from behind; (c) Light Intensity coherence: an overly bright can on a table; (d) Intersection coherence: a virtual chair partially intersecting with a table; (e) Floating plausibility: a virtual basketball suspended above a table; and (f) Size appropriateness: an oversized virtual apple on a table.</p> 

# Rule-based method mapping function and parameters

We provide the code of our factor estimation functions, the mapping function to map the estimated values to the quality scores, and the parameters for each function in the Rule_mapping_function.ipynb

# System instruction
Here is our full system instruction:
```
You will be provided with two images and a question:
1. The first image is a raw (unaltered) image.
2. The second image is an augmented reality (AR) image, created by adding virtual content to the scene. The virtual object can be eyeball, heart, balloon, basketball, and so on.\
Task:
Your task is to evaluate the quality of the AR image based on seven aspects from a fair human perception perspective. Each aspect should be rated on a scale from 1 to 5 (1: really bad, 2: seems bad, 3: not sure, 4: seems good, 5: very good) while considering the background environment. Additionally, you can describe the scene depicted in the AR image.
Evaluation Criteria:
1. **Visual Coherence** – Based on your first impression, how naturally does the virtual content appear within the real-world scene? If the content is meant to convey a purpose or message, does its appearance effectively support that?
2. **Size** – Comparing to the surrounding real objects, assess whether the size of the virtual object is appropriate. If surrounding real-world objects of a similar class are not in their typical size, the virtual object can also appear to be an atypical size. In medical AR applications, the size of the virtual medical model should reflect its typical real-world dimensions.
3. **Floating** – Determine whether the virtual object appears unnaturally floating when it should be grounded. If the surrounding real objects are designed to be floating or be throwing by the human, the virtual object can also be floating.
4. **Intersection** – Check if the virtual object is sinking into the vertical plane, the horizontal plane, or being penetrated by real objects.
5. **Occlusion** – Evaluate whether the virtual object obstructs critical real-world elements, such as caution signs, electrical devices, or safety equipment.
6. **Shadow** – Determine whether the virtual object should cast a shadow and if the shadow appears realistic. If the purpose of the AR scene is to demonstrate the size and location of the medical model, you can rate higher score to the shadow since shadow is irrelevant.
7. **Light Direction** – Assess whether the lighting direction of the virtual object aligns with that of the surrounding real-world objects. Shadow directions of the virtual and real objects can also be considered for this factor. If the purpose of the AR scene is to demonstrate the size and location of the medical model, you can rate higher score to the light direction since light direction is irrelevant.
8. **Light Intensity** – Compare the luminosity of the virtual object with the surrounding real-world environment and determine if the brightness level is appropriate. If the purpose of the AR scene is to demonstrate the size and location of the medical model, you can rate higher score when the medical model is bright unless it is too bright or dark to observe the details.
Output Format:
Provide your response in **JSON format** with the seven aspects as keys, assigning a score (1-5) to each aspect. Additionally, include a brief description of the AR scene.
Example Output1:
{
"scene_description": "A commonly-seen living room with a virtual chair placed near the table. The virtual chair blends seemlessly into the real-world scene for the first glance, but I feel that the light direction looks wired. The size of the virtual chair looks nomral in this working place. It is not floating at all. But it is sinking into the floor and obstructing a knife appearing in the raw image. The shadow looks smooth. The light drection is different significantly from the real-world objects. The virtual chair looks too bright comparing to the surrounding objects.",
"visual_coherence": 4,
"size": 4,
"floating": 5,
"intersection": 1,
"occlusion": 1,
"shadow": 4,
"light_direction": 1,
"light_intensity": 1
}
Example Output2:
{
"scene_description": "The AR image depicts a virtual heart model floating in a room next to a person. However, instead of being overlaid on the correct position of the human body, the heart appears in front of a wall, near a caution sign. So it does not blend well with the scene. It doesn't obstruct the caution sign. The heart size looks a little larger than a normal heart size. The shadow and lighting direction are not related to the medical model, so I'll give a higher score. The brightness is well-balanced, allowing the model’s details to be seen clearly.",
"visual_coherence": 1,
"size": 2,
"floating": 1,
"intersection": 5,
"occlusion": 5,
"shadow": 5,
"light_direction": 5,
"light_intensity": 4
}
```
# Task prompt
Here is our full task prompt:
```
I estimated several aspects of the AR image quality using traditional methods. These estimates may not be entirely reliable, but they may provide useful cues for evaluation. Here are the traditionally estimated values:
- **Size**: The virtual object is approximately $\Delta_S$ meters.
- **Floating**: The virtual object has a depth difference of around $\Delta_F$ meters with the background, and about $C_F$ of its bottom is in contact with a real-world object.
- **Intersection**: The virtual object has $N_{\text{intersec}}$ obvious parts.
- **Occlusion**: The virtual object, with a transparency level of $S$ and ${C_{\text{edge}}}$, is obstructing $V$.
Based on this information and your own analysis of the images, can you help me rate the AR image quality?
```
