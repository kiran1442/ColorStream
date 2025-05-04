# ColorStream: Real-Time Video Colorization

## Overview

A real-time colorization system that applies deep learning techniques to convert grayscale videos into vibrant color videos. The application processes video files or live webcam streams and displays the output with a side-by-side comparison and frame rate information. It uses a pre-trained Caffe model integrated through OpenCV.

---

## Features

- Real-time colorization of grayscale videos

- Processes both video files and single image frames

- Frame-per-second (FPS) performance indicator

- Outputs colorized video side-by-side with original

---

## Project Structure

├── models/
│   ├── colorization_deploy_v2.prototxt        # Model architecture
│   ├── colorization_release_v2.caffemodel     # Pre-trained model weights
│   └── pts_in_hull.npy                        # Cluster centers for ab channels
├── inputs/
│   └── grayscale_video.mp4                    # Sample input video
├── colorizer.py                               # Core processing and DNN pipeline
├── main.py                                    # Entry point for GUI (if extended)
├── README.md                                  # This file
├── requirement.txt                            # contains all the required packages

---

## Usage

1. Install dependencies:

```bash
pip install requirement.txt
```

2. Colorize Video File
- Add your grayscale video to the `inputs/` folder.

- In `colorizer.py`, ensure the correct input path is used.

Run the script:

```bash
python colorizer.py

```

---

## Model Overview

- **Base Network**: Caffe-based model trained on ImageNet

- **Input**: Grayscale image (L channel in LAB space)

- **Output**: Color (a, b) channels fused with L channel

- **Framework**: OpenCV’s `dnn` module (Caffe backend)

---