title: "Spatio‑Temporal Fire Segmentation"
description: "Deep learning framework for segmenting wildfire regions using spatio‑temporal convolutional networks with attention"
dateString: January 2025 - Current
draft: false
tags: ["Deep Learning", "Computer Vision", "Wildfire Detection", "PyTorch"]
weight: 200
cover:
image: "/projects/stcnn-fire/cover_fire_stcnn.png"
<style> /* Container to maintain aspect ratio for embedded videos */ .video-container { position: relative; width: 100%; padding-bottom: 56.25%; /* 16:9 aspect ratio */ height: 0; overflow: hidden; background: #000; } .video-container iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; } </style>
I devoted my final year research project to designing and evaluating a Spatio‑Temporal Convolutional Network for segmenting wildfire regions in aerial video. This work combines a deep segmentation network with a temporal GAN to enforce cross‑frame consistency and explores attention mechanisms to improve feature extraction. The resulting framework, STCNN_FIRE, is a complete pipeline for wildfire segmentation that can process video streams in real time.
Summary of contributions

- Implemented STCNN architecture: I developed a U‑Net–like segmentation branch with a ResNet‑101 encoder, a pyramid pooling module and a convolutional decoder, and paired it with a temporal branch based on a GAN with Inception v3 and ResNet‑101 backbones. The temporal branch encourages temporal coherence in the predicted masks.
Explored attention modules: To reduce parameters and focus the network on salient regions, I replaced the pyramid pooling module with a convolutional bottleneck attention module (CBAM). This substitution reduced the parameter count by roughly ten million while maintaining comparable performance.
- Conducted ablation studies: I evaluated variants of the model by removing the PPM (replacing it with a 1×1 bottleneck) and by disabling the temporal branch entirely. These experiments highlight how temporal information and attention affect segmentation quality.
Built a training pipeline: The system incorporates random cropping, horizontal flipping, rotations and normalization during training. Pre‑training used the MSRA10K and VOC2012 datasets for segmentation and DAVIS 2016 for the temporal branch, followed by joint fine‑tuning on the FLAME wildfire dataset.
- Evaluated performance: I reported intersection‑over‑union (IoU), mean pixel accuracy (PA), mean IoU and Dice score on the FLAME dataset. The full model achieved 71.87 % IoU, 91.88 % mean PA, 85.86 % mean IoU and 83.53 % Dice score after 200 epochs. Variants with CBAM and 1×1 bottlenecks achieved similar or slightly improved scores, while segmentation‑only models saw degraded performance.
The experiments underscore the importance of temporal information and attention mechanisms for accurate wildfire segmentation. They also illustrate the impact of dataset quality: FLAME provides high‑quality masks, whereas models trained on limited or poorly annotated data tend to over‑fit and generalize poorly.
- Model variants and results
To compare the different architectures, I summarised the final performance metrics at 200 epochs. The CBAM variant achieved 72.36 % IoU and the highest mean pixel accuracy at 95.05 %, while the 1×1 bottleneck variant achieved 72.80 % IoU and 93.89 % mean pixel accuracy. The original STCNN attained 71.87 % IoU and 91.88 % mean pixel accuracy. Removing the temporal branch reduced IoU to 70.40 %, and removing both the temporal branch and the PPM (using a 1×1 bottleneck) yielded 72.89 % IoU. These comparisons show that temporal coherence and attention modules contribute to reliable wildfire segmentation.
Attention module design:

The Convolutional Block Attention Module (CBAM) introduces channel‑wise and spatial attention to refine feature maps. By integrating CBAM into the segmentation branch, the network learns to emphasise relevant pixels and ignore irrelevant background. The diagram below illustrates the CBAM structure.

Segmentation examples:

Qualitative examples demonstrate that the full STCNN with a CBAM bottleneck produces accurate masks on both the FLAME dataset and generic wildfire video sequences. Temporal consistency reduces false positives and preserves fine details in the segmented regions.
Discussion and future work

This project shows that spatio‑temporal CNNs with attention can segment wildfire regions accurately in aerial video. The temporal branch improves coherence across frames, and attention modules like CBAM can reduce parameter counts while maintaining performance. However, the improvements over the baseline are modest; exploring transformer‑based temporal models and lightweight encoders (e.g., MobileNet or EfficientNet) could further reduce computational cost and improve accuracy. Additionally, collecting larger and more diverse datasets with high‑quality annotations is essential for improving generalisation beyond the FLAME dataset. Finally, integrating segmentation with downstream tasks such as fire spread forecasting and resource allocation would enhance the practical utility of this work.