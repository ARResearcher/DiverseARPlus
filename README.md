# DiverseAR+ Dataset
This repository accompanies the journal paper ["_Probing the Augmented Reality Scene Analysis Capabilities of Large Multimodal Models: Toward Reliable Real-Time Assessment Solutions_"]([https://arxiv.org/abs/2501.13964](https://ieeexplore.ieee.org/abstract/document/11207679?casa_token=qrYlU9VpLRYAAAAA:epj3Fi_GAIvh0jqcQUoNf07dtPtdLKrlSQaiGJ_Oi5-Ikv18d9GBSogaa8yB3Q_0XM05s0f_W8o)), published in IEEE Internet Computing 2025. It introduces **DiverseAR+**, a dataset of 1405 AR images collected from a public website (DeepAR), two commercial AR platforms (Amazon and Scaniverse), three AR applications previously developed by our lab running on Magic Leap, Android, and HoloLens, and three AR applications specifically created for this project running on Apple Vision Pro, HoloLens 2 and Android phones.

## Outline:
* [Motivation and Collection Process](#1)
* [Dataset Composition](#2)
* [Hierarchical Structure of the Datasets](#3)
* [Dataset Download](#4)
* [Citation](#5)
* [Acknowledgments](#6)

The rest of the repository is organized as follows. [**Section 1**](#1) briefly introduces the motivation behind creating the DiverseAR+ dataset and details the collection process. [**Section 2**](#2) presents the dataset composition. [**Section 3**](#3) describes the dataset structure. [**Section 4**](#4) provides the download link to the full dataset. The citation information, author contacts, and acknowledgments are introduced in [**Section 5**](#5) and [**Section 6**](#6). 

## 1. <span id="1"> Motivation and Collection Process</span> 
To evaluate the AR scene understanding capabilities of VLMs, we curated the DiverseAR dataset, specifically designed to capture a broad spectrum of AR scenarios. The dataset consists of **298 AR images** collected from diverse sources and environments. It includes 23 images captured using a custom-developed Apple Vision Pro AR application in laboratory and kitchen environments, and 151 images collected from a custom-developed Android AR application in bedroom and dining room environments. Additionally, 42 images were created to explore AR-specific research topics, such as attention patterns, virtual content arrangements, and surgical guidance. The dataset also features 7 images of glass objects obtained from the Amazon app's AR view and 46 images collected from the Scaniverse app's AR view, captured in laboratory, kitchen, and dining room environments. Finally, 29 images were sourced from a website showcasing AR advertisement videos. Additionally, we included **20 non-AR images** to supplement the dataset.

## 2. <span id="2"> Dataset Composition</span>

_Creation:_ The DiverseAR+ dataset comprises 1,405 AR images along with the associated metadata. Figure 1 presents representative AR examples from the DiverseAR+, illustrating a range of quality levels across all visual factors. We collected the samples from diverse sources and environments using commercial and custom-developed AR applications. Specifically, we captured 320 samples by Apple Vision Pro and 826 samples by Android phones (Galaxy S25 and Pixel 7) across various settings, including bedrooms, living rooms, study rooms, kitchens, and simulated museum environments, in which virtual objects were overlaid onto static museum images; 135 samples by HoloLens 2 in medical settings using virtual anatomical models; and 124 samples from external sources (29 public websites, 53 commercial apps, 42 prior studies). In addition, we recorded complementary metadata, including depth information (for Android devices and HoloLens 2) and the pose data of the camera, headset, virtual object, and virtual light in the scene to support further analysis. 

_Details:_ Each image features a single virtual object selected from a total of 29 classes. These span a range of domains including: medical anatomies of a human body (e.g., eye, brain, bone, liver, heart), dynamic, user-manipulable objects (e.g., basketball, football, glove), and stationary objects (e.g., chair, can, box, table, etc.). The dataset captures a diverse range of visual quality statuses across 3 factors, recognized as key dimensions of photorealistic coherence and user safety in AR: **shadow realism, floating plausibility, intersection coherence**.

<p align="center"><img width="600" alt="Representative AR examples from the DiverseAR+ dataset illustrating various quality levels across 3 visual factors." src="https://github.com/ARResearcher/ARQA/blob/main/images/DiverseAR+_samples.png"></p>
<p align="center">Figure 1. Representative AR examples from the DiverseAR+ dataset illustrating various quality levels across 3 visual factors: (1) Shadow realism: Virtual basket with fair shadow strength, rendered with opposite (poor), slightly different (slightly degraded), or same (good) direction as the real shadow; (2) Intersection coherence: Virtual toy dinosaur clearly intersecting a real bottle (poor), slightly sinking into the board (slightly degraded), or correctly positioned on the table (good); (3) Floating plausibility: Virtual energy-drink can that appears obviously detached (poor), slightly elevated (slightly degraded), or properly seated (good).</p> 

## 3. <span id="3"> Hierarchical Structure of the Datasets</span>
The dataset follows the hierarchical file structure shown below:
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

## 4. <span id="4"> Dataset Download</span> 
+ The full DiverseAR+ dataset can be downloaded here: [https://huggingface.co/datasets/I3TDataset/DiverseARPlus/tree/main/dataset](https://huggingface.co/datasets/I3TDataset/DiverseARPlus/tree/main/dataset).

## 5. <span id="5"> Citation</span>

If you use DiverseAR+ dataset in an academic work, please cite: .

     @inproceedings{Duan25DiverseARPlus,
      title={Probing the Augmented Reality Scene Analysis Capabilities of Large Multimodal Models: {T}oward Reliable Real-Time Assessment Solutions },
      author={Duan, Lin and Elias, Rotondo and Yanming, Xiu and Sangjun, Eom and Ryan, Chen and Conrad, Li and Yuhe, Hu and Gorlatova, Maria},
      journal={IEEE Internet Computing},
      year={2025},
      publisher={IEEE}
    }

## 6. <span id="6"> Acknowledgments</span> 

The contributors of the dataset are [Lin Duan](https://scholar.google.com/citations?user=3KGmyogAAAAJ&hl=en), Eli Rotondo, Sarah Eom, Ryan Chen, Conrad Li, and [Maria Gorlatova](https://maria.gorlatova.com/bio/). For questions on this repository or the related paper, please contact Lin Duan at ld213 [AT] duke [DOT] edu.

This work was supported in part by NSF grants CSR-2312760, CNS-2112562, and IIS-2231975, NSF CAREER Award IIS-2046072, NSF NAIAD Award 2332744, a CISCO Research Award, a Meta Research Award, Defense Advanced Research Projects Agency Young Faculty Award HR0011-24-1-0001, and the Army Research Laboratory under Cooperative Agreement Number W911NF-23-2-0224. The views and conclusions contained in this document are those of the authors and should not be interpreted as representing the official policies, either expressed or implied, of the Defense Advanced Research Projects Agency, the Army Research Laboratory, or the U.S. Government. This paper has been approved for public release; distribution is unlimited. No official endorsement should be inferred. The U.S. Government is authorized to reproduce and distribute reprints for Government purposes, notwithstanding any copyright notation herein.
