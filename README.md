# 3D Gaussian Splatting Project

## 📚 Table of Contents
1. [Project Setup](#project-setup)
2. [Data Preparation](#data-preparation)
3. [Using COLMAP (Local)](#using-colmap-local)
4. [Training the 3D Gaussian Splat (Colab)](#training-the-3d-gaussian-splat-colab)
5. [Results](#results)

---

## 🛠️ Project Setup
1. **FFmpeg Installation**  
   Begin by downloading FFmpeg from the official website and adding it to your system's path. This ensures that you can use FFmpeg commands globally. To do this, use the *Edit system environment variables* option in the *Advanced system settings* of Windows.

2. **COLMAP Setup**  
   Download COLMAP and place it in your C drive. After that, set the system path to COLMAP using the *Edit system environment variables* option, allowing COLMAP to be accessed from the command line.

---

## 📹 Data Preparation
1. **Select Your Video**  
   Choose a video (such as a personal recording) that you would like to convert into a 3D model.

2. **Clone the Repository**  
   Clone the 3D Gaussian Splatting repository to your local machine using the following command:
   ```bash
   git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive

   

