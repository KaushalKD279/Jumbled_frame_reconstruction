# 🧩 Jumbled Frames Reconstruction Challenge

## 🎯 Objective
Reconstruct the original 5-second, 1080p, 60 FPS video from a shuffled version (`jumbled_video.mp4`) by restoring the correct frame order using feature-based similarity analysis.

---

## ⚙️ Dependencies
This notebook automatically installs all required dependencies.

Algorithm Overview

The reconstruction process is based on frame similarity using deep features extracted from a pretrained ResNet-50 model.

Steps:

Frame Extraction:
All frames are decoded and stored in memory.

Feature Extraction:
Each frame is passed through a pretrained CNN (ResNet-50) to extract 2048-dimensional embeddings.

Similarity Matrix Computation:
Cosine similarity is computed between all frame features using GPU acceleration.

Greedy Path Construction:
Frames are ordered by iteratively selecting the most similar next frame.

2-opt Local Optimization:
A limited 2-opt heuristic is applied to improve global sequence ordering based on similarity gain.

Video Reconstruction:
Frames are written sequentially to produce the final output reconstructed.mp4.
