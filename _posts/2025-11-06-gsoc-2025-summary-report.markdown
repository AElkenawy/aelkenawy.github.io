---
layout: post
title:  "GSoC 2025 – Project Summary [ICSW]"
date:   2025-11-06 15:00:00 +0200
categories: GSoC TLF AGL
permalink: /gsoc25-tlf-project-summary/
---
# Intelligent Camera Stream Integration and Warning System (ICSW)


The Project Summary provides an overview about Intelligent Camera Stream Integration and Warning System **ICSW** project,
which was part of the [Google Summer of Code][1] (GSoC) 2025 program. The **ICSW** project was mentored by 
[The Linux Foundation (TLF)][2] through its [Automotive Grade Linux (AGL)][3] open source initiative. 
The purpose of the **ICSW** project was to develop a modular system that servers as a warning system for automotive application. 

As part of this work, the project focused on:

1. Researching and benchmarking the capabilities of different hardware backends for automotive applications
2. Detecting and classifying environmental objects that directly affects the driving behavior in real time
3. Visualizing relevant detected objects and conveying appropriate warning messages.


The progress achieved so far lays the foundations for the planned **ICSW** system. The work completed during the Google 
Summer of Code 2025 program managed to address the following components of the system:
1. **Inference models** [cam_infer_models][4] 
- for detecting surrounding objects and traffic signs.
2. **PipeWire Multimedia Layer** (co-hosted in [cam_infer_models][4])
- for managing and controlling the flow of camera streams.
3. **Flutter Application** [camera_streams_app][5] 
- for visual demonstration of retrieved and processed camera streams, and user visual warnings.
4. **gRPC Communication Layer** (protos in [camera_idl][6])  
- for intercommunication between system components, and for activating or switching detection modes.

## Project Highlights
The planned timeline for the GSoC 2025 program for large projects spans 22 weeks. The following table provides 
references for each week's progress regarding the **ICSW** system development:

| [Week 1][7]   | [Week 2][8]   | [Week 3][9]   | [Week 4*][10]  |  [Week 5][11]   |       [AMM][12]       |
| [Week 7][13]  | [Week 8][14]  | [Week 9*][15]  | [Week 10][16] |  [Week 11*][17]  | **Midterm Evaluation**|
| [Week 12][18] | [Week 13][19] |     Break     |     Break     |  [Week 16*][20]  |         Break         |
| [Week 18][21] | [Week 19][22] | [Week 20][23] | [Week 21][24] |  [Week 22*][25]  | **Final Evaluation**  |

The figure below illustrates my dedicated working hours throughout the GSoC 2025 program timeline:

<a name="fig1-gsoc25-hours"></a>
![GSoC25 work hours](/assets/images/gsoc25_sum/sum_fig1.png){:style="max-width:120%;height:auto;"}
**Figure 1.** Weekly Working Hours During GSoC 2025

During the program, the following milestones contributed most significantly to the final outcome of the 
**ICSW** application: 

1. [Week 4][10]: Three-node PipeWire graph that produces two video streams.
2. [Week 9][15]: PipeWire graph that processes live camera input and hosts objects detector on the detection playback stream
3. [Week 11][17]: Flutter application capable of communicating with inference model(s) and retrieving object detections 
4. [Week 15][20]: First [PR #1][26] to be merged for the environment CI job
5. [Week 22][25]: Submitted Gerrit change [#31262][30] containing the finalized Yocto recipes, and built the AGL Image

The following table describes the submitted Pull Requests along with their status throughout the project:

| Repository | PR | Status | Description |
| [cam_infer_models][4] | [PR #1][26]  | ✅ merged | YOLO CI Job |
| [cam_infer_models][4] | [PR #2][27]  | ✅ merged  | TFLite, CI Job |
| [cam_infer_models][4] | [PR #3][28]  | 🚧 ongoing | Refactoring |
| [camera_idl][6]       | [PR #1][29]  | ✅ merged  | Refactoring |
| [meta-agl-demo][31]   | [Change #31262][30]  | ✅ merged  | ICSW Integration |

## Key Takeaways

1. Learned about the **Yocto** Project, its components (recipes and layers), and how to use **Gerrit** effectively.
2. Gained some experience developing **Flutter** applications and organizing PipeWire graphs.
3. Implemented the communication layer using **gRPC**.
4. Understood how to use GitHub actions workflow with **CI jobs**
5. Realized the importance of not getting stuck in planning or reading documentation, but to start creating tangible code
early instead. Special thanks to [Joel](mailto:joel.winarske@toyotaconnected.com) for emphasizing this point.
6. Learned that regaining momentum quickly after breaks is vital to achieving goals.
This challenge is clearly observed in [Figure&nbsp;1](#fig1-gsoc25-hours), which shows reduced hours after 
the midterm and vacation weeks.

## Future Work

1. Enhancement and continued contribution to the **ICSW** system, including completion of pending tasks:
   - Improve SSD-Mobilenet TFLite model
   - Enhance the Flutter Application lifecycle management
   - Merge the [PR #3][28]
   - Documentation
2. Hardware implementation on the NanoPC-T6.
3. Continuous contribution to the [AGL][3] project.

## Acknowledgments
I am deeply grateful for the opportunity to participate in the [GSoC][1] program and contribute to [AGL][3] this year.
I would like to highlight the invaluable guidance and continuous support provided by my mentors, throughout the project,
as well as the great role of the AGL community. 
Special thanks go to my mentors 
[Joel](mailto:joel.winarske@toyotaconnected.com), [Jan-Simon](mailto:jsmoeller@linuxfoundation.org), 
[George](mailto:george.kiagiadakis@collabora.com), [Walt](mailto:wminer@linuxfoundation.org), 
and [Scott](mailto:scott.murray@konsulko.com) from whom I have learned a lot, both technically and personally.

[1]: https://summerofcode.withgoogle.com/
[2]: https://www.linuxfoundation.org/projects
[3]: https://www.automotivelinux.org/
[4]: https://github.com/AElkenawy/cam_infer_models/
[5]: https://github.com/AElkenawy/camera_streams_app
[6]: https://github.com/AElkenawy/camera_idl

[7]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/06/06/gsoc-2025-w1su.html
[8]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/06/12/gsoc-2025-w2su.html
[9]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/06/19/gsoc-2025-w3su.html
[10]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/06/27/gsoc-2025-w4su.html
[11]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/07/04/gsoc-2025-w5su.html
[12]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/07/11/gsoc-2025-w6su.html
[13]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/07/18/gsoc-2025-w7su.html
[14]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/07/25/gsoc-2025-w8su.html
[15]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/08/01/gsoc-2025-w9su.html
[16]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/08/08/gsoc-2025-w10su.html
[17]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/08/17/gsoc-2025-w11su.html

[18]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/08/24/gsoc-2025-w12su.html
[19]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/09/01/gsoc-2025-w13su.html
[20]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/09/21/gsoc-2025-w16su.html
[21]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/10/05/gsoc-2025-w18su.html
[22]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/10/13/gsoc-2025-w19su.html
[23]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/10/19/gsoc-2025-w20su.html
[24]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/10/26/gsoc-2025-w21su.html
[25]: https://aelkenawy.github.io/gsoc/tlf/agl/2025/11/02/gsoc-2025-w22su.html

[26]: https://github.com/AElkenawy/cam_infer_models/pull/1
[27]: https://github.com/AElkenawy/cam_infer_models/pull/2
[28]: https://github.com/AElkenawy/cam_infer_models/pull/3
[29]: https://github.com/AElkenawy/camera_idl/pull/1
[30]: https://gerrit.automotivelinux.org/gerrit/c/AGL/meta-agl-demo/+/31262
[31]: https://gerrit.automotivelinux.org/gerrit/AGL/meta-agl-demo
