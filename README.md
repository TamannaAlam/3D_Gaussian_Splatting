# 3D Gaussian Splatting Project

## 📚 Table of Contents
1. [Project Setup](#project-setup)
2. [Data Preparation](#data-preparation)
3. [Using COLMAP (Local)](#using-colmap-local)
4. [Training the 3D Gaussian Splat (Colab)](#training-the-3d-gaussian-splat-colab)

---

## 🛠️ Project Setup
1. **FFmpeg Installation**  
   - Download **FFmpeg** from the official website.  
   - Add FFmpeg to the system path to enable command-line access.  
   - To add FFmpeg to the path, use *Edit system environment variables* under *Advanced system settings* in Windows.  

2. **COLMAP Setup**  
   - Download **COLMAP** and place it in the **C drive** for easy access.  
   - Set the system path for COLMAP using the *Edit system environment variables* option.  
   - This allows you to run COLMAP from the command line.

3. **ImageMagick Installation**  
   - Download **ImageMagick** from [the official website](https://imagemagick.org/script/download.php), or use the installer you've uploaded.  
   - Run the installer (`ImageMagick-7.1.1-41-Q16-HDRI-x64-dll.exe`) and follow the setup instructions.  
   - During installation, ensure that the option to add ImageMagick to your system path is selected, so you can run it from the command line.

---

## 📹 Data Preparation
1. **Select Your Video**  
   - Choose a **random video** (e.g., a personal recording) that you want to convert into a 3D model.  

2. **Clone the Repository**  
   - Clone the 3D Gaussian Splatting repository from GitHub using the following command:  
     ```bash
     git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive
     ```
   - Navigate to the cloned repository:  
     ```bash
     cd gaussian-splatting
     ```

3. **Place the Video in the Directory**  
   - Place your video file (for example, **my_random_video.mp4**) inside the `gaussian-splatting` folder.  

4. **Create a Folder and Extract Frames**  
   - Create a folder named **test** inside the `gaussian-splatting` directory.  
   - Run the following **FFmpeg** command to extract frames from the video:  
     ```bash
     ffmpeg -i your_video_name.mp4 -qscale:v 1 -qmin 1 -vf fps=10 test/%04d.jpg
     ```
     **Note**: Replace `your_video_name.mp4` with the name of your video file. This command extracts frames from the video at 10 frames per second and saves them as high-quality images in the **test** folder.  

5. **Organize and Prepare the Images**  
   - Select all the extracted images from the **test** folder.  
   - Cut and paste them into a new folder named **input** inside the **test** folder.  

6. **Run the Image Conversion Script**  
   - Use the **convert.py** script to process the images. This script resizes the images and adjusts the camera perspective.  
   - Run the following command:  
     ```bash
     python convert.py -s test --resize --camera PINHOLE
     ```

---

## 🗺️ Using COLMAP (Local)
1. **Launch COLMAP**  
   - Go to the **COLMAP** folder in the **C drive**.  
   - Run **colmap.bat** to open the COLMAP user interface (UI).  

2. **Import Data into COLMAP**  
   - In the COLMAP UI, import the following folder:  
     ```
     test --> sparse --> 0
     ```

3. **Prepare Data for Google Colab**  
   - Keep only the **image** and **sparse** folders from the **test** directory.  
   - Compress these two folders into a **zip file**.  
   - Upload the **zip file** to a cloud storage platform like **Google Drive** for use in the next steps.  

---

## 🚀 Training the 3D Gaussian Splat (Colab)
1. **Run the Colab Notebook**  
   - Open **Google Colab** and run the **gaussian_splatting_colab.ipynb** notebook.  
   - Make sure to set up the correct paths to the **image** and **sparse** files that you uploaded to **Google Drive**.  
   - Follow the steps in the notebook to train the 3D Gaussian Splat model.  
