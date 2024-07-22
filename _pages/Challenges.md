---
layout: page
permalink: /challenge/
title: Challenges
description: 
nav: true
nav_order: 3
---


<!-- ### Two Open-Source Datasets 

Two open-source datasets are provided for this workshop. The first dataset focuses on extracting traffic language from HD maps to aid in traffic scenario comprehension through LLMs. The second dataset aims to categorize textbased driver commands to improve human-vehicle language understanding. While using the datasets is recommended, it is **not mandatory** for participation. Both datasets will be released on **Sep. 15th**. 

#### Dataset 1
TBD

#### Dataset 2
TBD -->

Two open-source datasets are provided for this workshop. The first dataset focuses on extracting traffic language from
HD maps to aid in traffic scenario comprehension through LLVMs. The second dataset aims to categorize textbased driver
commands to improve human-vehicle language understanding. While using the datasets is recommended, it is
**not mandatory** for participation. 

----------

### Challenge 1: MAPLM: A Large-Scale Vision-Language Dataset for Map and Traffic Scene Understanding

**[Data Download](https://drive.google.com/drive/folders/1cqFjBH8MLeP6nKFM0l7oV-Srfke-Mx1R?usp=sharing); [Git Repo](https://github.com/LLVM-AD/MAPLM)**

Tencent Maps HD Map T.Lab, in collaboration with the University of Illinois at Urbana-Champaign, Purdue University, and the University of Virginia, have launched the industry's first multimodal language+vision (point cloud BEV+panoramic images) traffic scenario understanding dataset: MAPLM. MAPLM provides abundant road scenario images complemented with multi-level scene description data, aiding models in navigating complex and varied traffic environments. 

#### Data Download:

Put the maplm v0.1.z01, maplm v0.1.z02, maplm v0.1.z03, maplm v0.1.zip into one directory then run the following command to unzip the dataset.
```bash
zip -s 0  maplm_v0.1.zip --out combine.zip
unzip combine.zip
```

#### Scene of MAPLM：    
MAPLM offers a variety of traffic scenarios, including highways, expressways, city roads, and rural roads, along with detailed intersection scenes. Each frame of data includes two components:           
- **Point Cloud BEV:** A projection image of 3D point cloud viewed from the BEV perspective with clear visuals and high resolution.        
- **Panoramic Images:** High-resolution photographs captured from front, left-rear, and right-rear angles by a wide-angle camera.    

#### Annotations：    
- **Feature-level:** Lane lines, ground signs, stop lines, intersection areas, etc.        
- **Lane-level:** Lane types, directions of traffic, turn categories, etc.       
- **Road-level:** Scene types, road data quality, intersection structures, etc.     

#### Data Display：    
Point Cloud BEV image + 3 panoramic photos. Note: Panoramic images are 4096*3000 portrait shots. The image below is only a cropped sample.<br /> 

<div class="msg_desc">
<img style="max-width:100%;overflow:hidden;" src="https://raw.githubusercontent.com/LLVM-AD/MAPLM/main/figures/example1.png" alt="">
</div>
<!-- ![Poster]([./figures/example1.png](https://raw.githubusercontent.com/LLVM-AD/MAPLM/main/figures/example1.png)) -->
<br />

#### Label Display：    
The image below illustrates one frame's annotation information, encompassing three parts: road-level information (in red font), lane-level information (yellow geometric lines + orange font), and intersection data (blue polygons + blue font).<br />         

<!-- ![Poster]([./figures/example2.png](https://raw.githubusercontent.com/LLVM-AD/MAPLM/main/figures/example.png)) -->
<div class="msg_desc">
<img style="max-width:100%;overflow:hidden;" src="https://raw.githubusercontent.com/LLVM-AD/MAPLM/main/figures/example2.png" alt="">
</div>

<br />

----------

### Challenge 2: In-Cabin User Command Understanding (UCU)

**[Data Download](https://github.com/LLVM-AD/ucu-dataset/blob/main/ucu.csv); [Code for Evaluation](https://github.com/LLVM-AD/ucu-dataset)**

The future of autonomous vehicles is not only to transport passengers from point A to point B, but also to adapt to
their needs and preferences. Large Language Models (LLMs) have provided an opportunity to advance the state-of-the-art
of this vision. This dataset focuses on understanding user commands in the context of autonomous vehicles.

#### Data

The dataset contains 1,099 labeled commands. Each command is a sentence that describes a user's request to the
vehicle. For example, "Overtake the car in front of me". The objective is to answer the following 8 Yes/No questions
about executing the command in an autonomous vehicle:

1. Is the `external perception system` required?
2. Is `in-cabin monitoring` required?
3. Is `localization` required?
4. Is `vehicle control` required?
5. Is the `entertainment system` required?
6. Is `user personal data` required?
7. Is `external network access` required?
8. Is there a possibility of `violating traffic laws`?

The following definitions explain the terms used in the questions:

1. `external perception system` refers to the sensors and software that allow the autonomous vehicle to perceive its
   surroundings. It typically includes cameras, lidar, radar, and other sensors to detect objects, pedestrians, other
   vehicles, road conditions, and traffic signs/signals.
2. `in-cabin monitoring` involves cameras, thermometers, or other sensors placed inside the vehicle's cabin to monitor
   the state of occupants and other conditions.
3. `localization` is the ability of the vehicle to determine its precise position in a given environment. Typically done
   using a combination of GPS, sensors, and high-definition maps.
4. `vehicle control` refers to the system that makes the driving decisions and physically controls the vehicle
   movements, such as steering, acceleration, braking, and signaling.
5. `entertainment system` is the multimedia system in a vehicle, which can include radio, music players, video displays,
   and other entertainment features.
6. `user personal data` is the information relating to an identified or identifiable individual, such as contact
   details, preferences, travel history, etc.
7. `external network access` is the ability of the vehicle's systems to connect to external networks, such as the
   internet or cloud services.
8. `violating traffic laws` refers to any action performed by the vehicle that goes against the established traffic
   regulations of the region. An autonomous vehicle's system is typically designed to adhere strictly to traffic laws.

The participants are encouraged to use open-source LLMs to answer the questions with *in-context learning* to explore
the reasoning ability of LLMs in understanding user commands. The provided commands are for evaluation, while the
participants are free to use any other data for training or come up with their own examples for prompt engineering.

#### Evaluation

To use the provided code for evaluation, the output should be in the following format:

`<command_id> <A1> <A2> <A3> <A4> <A5> <A6> <A7> <A8>`

where `<command_id>` is the command numeric identifier, starting with 1. Command IDs have been
provided in the CSV file in the data download link.
`<A1>` to `<A8>` are the answers to the 8 questions, where 1 indicates "Yes" and 0 indicates "No".

We use two accuracy metrics for evaluation:

1. **Command-level accuracy**: A command is considered correctly understood if all eight answers are correct.
2. **Question-level accuracy**: Evaluation at the individual question level.

----------

### Citation       
If the code, datasets, and research behind this workshop inspire you, please cite our work:      
```
@inproceedings{tang2023thma,
  title={THMA: tencent HD Map AI system for creating HD map annotations},
  author={Tang, Kun and Cao, Xu and Cao, Zhipeng and Zhou, Tong and Li, Erlong and Liu, Ao and Zou, Shengtao and Liu, Chang and Mei, Shuqi and Sizikova, Elena and Zheng, Chao},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={37},
  number={13},
  pages={15585--15593},
  year={2023}
}
```

```
@article{zheng2023hdmap,
  title={High-Definition Map Automatic Annotation System Based on Active Learning},
  author={Zheng, Chao and Cao, Xu and Tang, Kun and Cao, Zhipeng and Sizikova, Elena and Zhou, Tong and Li, Erlong and Liu, Ao and Zou, Shengtao and Yan, Xinrui and Mei, Shuqi},
  journal={AI Magazine},
  year={2023},
  publisher={Wiley Online Library}
}
```
