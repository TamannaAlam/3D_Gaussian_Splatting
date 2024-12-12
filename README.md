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

   After cloning, navigate to the repository directory:

bash
Copy code
cd gaussian-splatting
Place your selected video file inside this directory.

Extract Frames from the Video
Create a folder named test, then use the FFmpeg command to extract frames from your video:

bash
Copy code
ffmpeg -i vid2.mp4 -qscale:v 1 -qmin 1 -vf fps=10 test/%04d.jpg
This command extracts frames at 10 frames per second, ensuring the images are of high quality.

Organize and Prepare Images
After selecting and cropping the extracted frames, create a new folder named input inside the test directory. Move your images into this folder and run the following Python script to process the images:

bash
Copy code
python convert.py -s test --resize --camera PINHOLE
🗺️ Using COLMAP (Local)
Launch COLMAP Locally
Open the COLMAP folder and run colmap.bat to launch the COLMAP user interface on your local machine.

Import Your Data into COLMAP
In COLMAP, import the test folder and then navigate to the sparse folder. Select 0 to start the structure-from-motion process.

Prepare Data for Upload
After the COLMAP processing, keep only the image and sparse folders. Compress them into a zip file and upload it to a cloud storage service, such as Google Drive
