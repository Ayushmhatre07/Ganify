# 🎨 GAnify: Interactive Image Manipulation Using GANs

An experimental project for interactive image editing using Generative Adversarial Networks (GANs). Inspired by DragGAN (SIGGRAPH 2023), this project allows users to manipulate generated images with precision by dragging key points.

## 🚀 Key Features

- Point-based interactive manipulation
- Real-time image generation and transformation
- Pre-trained StyleGAN2/3 support
- GUI and Gradio Web Interface
- Docker-ready for deployment

## 🧰 Tech Stack

- Python 3.8+
- PyTorch
- StyleGAN2/3
- Gradio (for web demo)
- OpenCV
- Docker (optional)

## ⚡ Performance Tip (Windows Users)

> 🖥️ **For best performance on Windows, it is strongly recommended to run this project under [WSL2 (Windows Subsystem for Linux)](https://learn.microsoft.com/en-us/windows/wsl/).**

- WSL2 provides native support for Linux-based GPU acceleration via CUDA.
- Set up your conda environment and run all shell scripts via WSL (Ubuntu).
- Docker can also utilize GPU in WSL if properly configured.

## 🖥️ Usage

### Installation

```bash
conda env create -f environment.yml
conda activate ganify
pip install -r requirements.txt
sh scripts/gui.sh  # for Linux/macOS or WSL
.\scripts\gui.bat  # for native Windows (not recommended)
python visualizer_drag_gradio.py
python scripts/download_model.py
docker build . -t ganify:latest
docker run -p 7860:7860 -v "$PWD":/workspace/src -it ganify:latest bash
cd src && python visualizer_drag_gradio.py --listen
