---
layout: page
permalink: /datasets/
title: Datasets
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
**not mandatory** for participation. Both datasets will be released on **Sep. 15th**.

### Dataset 1: MAPLM

TBA

### Dataset 2: In-Cabin User Command Understanding (UCU)

[Data Download](https://github.com/LLVM-AD/ucu-dataset/blob/main/ucu.csv); [Code for Evaluation](https://github.com/LLVM-AD/ucu-dataset)

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

1. Command-level accuracy: The command is considered correct if all 8 answers are correct.
2. Question-level accuracy: The question is considered correct if the answer is correct.