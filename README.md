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
How to Run

Open the notebook in Google Colab.

Run all cells sequentially.

The code will automatically:

Install dependencies

Download the jumbled video from Google Drive

Process and reconstruct the video

Generate an output file named reconstructed.mp4

After completion, the reconstructed video will be available for download.

⏱️ Execution Log

The notebook prints time taken for each major step:

Frame decoding

Feature extraction

Similarity matrix computation

Greedy path construction

2-opt optimization

Video writing

Total time

📦 Output

Input: jumbled_video.mp4 (downloaded automatically)

Output: reconstructed.mp4 (saved in the working directory)

🧩 Key Features

GPU-accelerated deep feature extraction (ResNet-50)

Cosine similarity matrix computed on GPU

Greedy + 2-opt optimization for ordering

Batched processing for efficient memory use

Complete in-memory pipeline with detailed runtime logs
