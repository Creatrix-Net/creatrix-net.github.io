---
layout: distill
title: Mind Controlled Bionic Arm with Sense of Touch
description: Imagine a prosthetic arm that functions like your natural arm. You wear a headband, and with the thought process, the working signal from mind connects to the prosthetic about moving the arm, it responds accordingly—just like your real arm!
tags: Bionic Arm Robotics Biotechnology Mind Control Prosthetics
giscus_comments: true
citation: true
img: /assets/img/mcba_logo.jpeg
date: 2024-12-12
featured: true
importance: 1
category: work
mermaid:
  enabled: true
  zoomable: true
code_diff: true
chart:
  chartjs: true
  echarts: true
  vega_lite: true
tikzjax: true
typograms: true

authors:
  - name: Dhruva Shaw
    url: "https://dhruvashaw.in"
    affiliations:
      name: Creative Net
  - name: Arittrabha Sengupta
    url: "https://arittrabha-biotech.pages.dev"
    affiliations:
      name: Creative Net
  - name: Jay Baswaraj Khaple
    url: "mailto:khaplejay00@gmail.com"
    affiliations:
      name: Lovely Professional University
  - name: Bhavya Choudhary
    url: "mailto:choudharybhavya225@gmail.com"
    affiliations:
      name: Lovely Professional University
  - name: Dr. G. Raam Dheep
    url: "mailto:raam.25227@lpu.co.in"
    affiliations:
      name: Lovely Professional University

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - align: right
    image: prof_pic.jpg
    content: profile/about_dhruva.md
    image_circular: false # crops the image to make it circular
    more_info: >
      <p>Dhruva Shaw</p>
      <p><a href="mailto:dhruvashaw@ieee.org">dhruvashaw@ieee.org</a></p>
      <p><a href="mailto:me@dhruvashaw.in">me@dhruvashaw.in</a></p>
      <p><a href="https://dhruvashaw.in" target="_blank">dhruvashaw.in</a></p>
  - align: left
    image: at.png
    content: profile/about_arittrabha.md
    image_circular: false # crops the image to make it circular
    more_info: >
      <p>Arittrabha Sengupta</p>
      <p><a href="https://arittrabha-biotech.pages.dev"  target="_blank">arittrabha-biotech.pages.dev</a></p>
      <p><a href="mailto:arittrabhasengupta@gmail.com">arittrabhasengupta@gmail.com</a></p>

bibliography: papers.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc: true

_styles: >
    .container {
        position: relative;
        overflow: hidden;
        width: 100%;
        padding-top: 56.25%; /* 16:9 Aspect Ratio (divide 9 by 16 = 0.5625) */
    }

    /* Then style the iframe to fit in the container div with full height and width */
    .responsive-iframe {
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        width: 100%;
        height: 100%;
    }
---

## Abstract

Advancements in bionic technology are transforming the possibilities for restoring hand function in individuals with amputations or paralysis. This paper introduces a **cost-effective bionic arm** design that leverages **mind-controlled functionality** and integrates a **sense of touch** to replicate natural hand movements. The system utilizes a **non-invasive EEG-based control mechanism**, enabling users to operate the arm using brain signals processed into PWM commands for servo motor control of the bionic arm. Additionally, the design incorporates a touch sensor (tactile feedback) in the gripper, offering sensory feedback to enhance user safety and dexterity.
The proposed bionic arm prioritizes three essential features:
1. **Integrated Sensory Feedback**: Providing users with a tactile experience to mimic the sense of touch (signals directly going to the brain). This capability is crucial for safe object manipulation by arm and preventing injuries
2. **Mind-Control Potential**: Harnessing EEG signals for seamless, thought-driven operation.
3. **Non-Invasive Nature**: Ensuring user comfort by avoiding invasive surgical procedures.
This novel approach aims to deliver an intuitive, natural, and efficient solution for restoring complex hand functions.

---

## Methodology
### 1. Data Collection and Dataset Overview
The model development utilized a publicly available EEG dataset comprising data from **60 volunteers** performing **8 distinct activities** [3]. The dataset includes a total of **8,680 four-second EEG recordings**, collected using **16 dry electrodes** configured according to the **international 10-10 system** [3].
* Electrode Configuration: Monopolar configuration, where each electrode's potential was measured relative to neutral electrodes placed on both earlobes (ground references).
* Signal Sampling: EEG signals were sampled at **125 Hz** and preprocessed using:
    - **A bandpass filter (5–50 Hz)** to isolate relevant frequencies [3].
    - **A notch filter (60 Hz)** to remove powerline interference [3].

### 2. Data Preprocessing
The dataset, originally provided in **CSV format**, underwent a comprehensive preprocessing workflow:
* The data was split into individual CSV files for each of the 16 channels, resulting in an increase from **74,441** files to **1,191,056** files.
* Each individual channel's EEG data was converted into **audio signals** and saved in **.wav format**, allowing the brain signals to be audibly analyzed.
* The entire preprocessing workflow was implemented in **Python** to ensure scalability and accuracy.
The dataset captured brainwave signals corresponding to the following activities:
1. **BEO** (Baseline with Eyes Open): One-time recording at the beginning of each run [3].
2. **CLH** (Closing Left Hand): Five recordings per run [3].
3. **CRH** (Closing Right Hand): Five recordings per run [3].
4. **DLF** (Dorsal Flexion of Left Foot): Five recordings per run [3].
5. **PLF** (Plantar Flexion of Left Foot): Five recordings per run [3].
6. **DRF** (Dorsal Flexion of Right Foot): Five recordings per run [3].
7. **PRF** (Plantar Flexion of Right Foot): Five recordings per run [3].
8. **Rest**: Recorded between each task to capture the resting state [3] [4].

### 3. Feature Extraction and Classification
Feature extraction and activity classification were performed using **transfer learning** with **YamNet** [5], a deep neural network model.
* **Audio Representation**: Audio files were imported into **MATLAB** using an **Audio Datastore** [6]. Mel-spectrograms, a time-frequency representation of the audio signals, were extracted using the yamnetPreprocess [7] function [8].
* Dataset Split: The data was divided into **training (70%)**, **validation (20%)**, and **testing (10%)** sets.
Transfer Learning with YamNet [5] [8]:
- The **pre-trained YamNet model** (86 layers) was adapted for an 8-class classification task:
    + The initial layers of YamNet [5] were **frozen** to retain previously learned representations [8].
    + A **new classification layer** was added to the model [8].
- Training details:
    + **Learning Rate**: Initial rate of **3e-4**, with an exponential learning rate decay schedule [8].
    + **Mini-Batch Size**: 128 samples per batch.
    + **Validation**: Performed every **651 iterations**.

### 4. Robotic Arm Design and Simulation
A **3-Degree-of-Freedom (DOF) robotic arm** was designed using **MATLAB Simulink** and **Simscape toolboxes**. To ensure robust validation:
* A **virtual environment** was developed in Simulink, simulating the interactions between the trained AI models and the robotic arm.
* The simulations served as a testbed to evaluate the system's performance before real-world integration.

### 5. Project Progress and Future Directions
_Completed Tasks_:
1. **AI Model Development**: Successfully trained models to classify human activities based on EEG signals.
2. **Robotic Arm Design**: Designed a functional 3-DOF robotic arm with simulated controls.
3. **Virtual Simulation**: Validated AI-robotic arm interactions in a virtual environment.

_Future Directions_:
1. **Hardware Integration**: Implement the developed AI models into physical robotic hardware for real-world testing.
2. **Real-Time EEG Acquisition**: Develop a system for **real-time EEG data acquisition** and activity classification.
3. **Tactile Feedback System**: Integrate tactile sensors with the robotic arm for **real-world sensory feedback**, complemented by Simulink-based simulations.

---

## Protocols
Here is the protocol(steps) to reproduce our work with ease.
<iframe src="https://www.protocols.io/widgets/doi?uri=dx.doi.org/10.17504/protocols.io.n92ldr869g5b/v1" style="width: 100%; height: 300px; border: 1px solid transparent;"></iframe>
<div class="container">
    <object data='{{ "/assets/pdf/protocol_mcba.pdf" | relative_url  }}' class="responsive-iframe" type='application/pdf'/>
</div>

---

{% include "profiles.liquid" %}
