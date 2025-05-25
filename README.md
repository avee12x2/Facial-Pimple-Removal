# Hybrid Approach to Automated Facial Pimple Removal

## 📌 Overview

This project presents a **hybrid pipeline** for automated pimple removal in facial images by combining classical image processing with deep learning-based inpainting techniques. It is designed to work without the need for any external dataset, making it data-efficient and highly adaptable.

## ✨ Features

- **Facial Landmark Detection** using Dlib and Face Alignment Network (FAN)
- **Adaptive Pimple Detection** using:
  - LAB color space thresholding
  - Gaussian blur-based local intensity differences
- **Inpainting Approaches**:
  - Classical method using OpenCV's Telea algorithm
  - Deep Image Prior (DIP) with a custom U-Net (no training dataset required)
- **Dynamic selection** of the best detection method per image
- **Quantitative Evaluation** with recall scores and qualitative comparison

## 🔍 Methodology

### 1. Facial Region Analysis
- 68-point Dlib landmarks + 3 custom forehead landmarks
- Convex hull generation to isolate facial area

### 2. Pimple Detection
- LAB A-channel thresholding (for redness)
- Gaussian-blur difference method
- Morphological operations to refine masks

### 3. Inpainting
- **OpenCV Telea**: Fast and light
- **Deep Image Prior**: Realistic, structure-preserving skin restoration

## 📊 Results

| Detection Method             | Mean Recall |
|-----------------------------|-------------|
| LAB Color Space Thresholding| 0.442       |
| Blur Difference (A-channel) | 0.498       |

| Inpainting Method           | Visual Quality | Processing Time |
|----------------------------|----------------|-----------------|
| OpenCV Telea               | Good           | Fast            |
| Deep Image Prior (DIP)     | Excellent      | Slower          |

## 📁 Dataset & Links

- 📄 [Google Colab Notebook](https://colab.research.google.com/drive/12OPdjwGulsCcBHLo3dCcinmn9tyLUxN2?usp=sharing)
- 📂 [Sample Dataset](https://drive.google.com/drive/folders/1I0i2bxpgjzVXhpGR6oiD8Jy4OciE80j-?usp=sharing)

## 🔬 Novel Contributions

- A **hybrid system** integrating both traditional and deep learning methods
- **Training-free** inpainting using DIP tailored per image
- **Landmark-enhanced facial masking**, including custom forehead points
- **Dynamic method selection** for pimple detection based on recall performance

## 🧑‍💻 Authors

- **Aarav Oswal** – [aaravoswal23@iitk.ac.in](mailto:aaravoswal23@iitk.ac.in)
- **Aryavart** – [aryavart23@iitk.ac.in](mailto:aryavart23@iitk.ac.in)
- **Somya Garg** – [somyagarg23@iitk.ac.in](mailto:somyagarg23@iitk.ac.in)

## 📜 License

This project is intended for educational and research purposes only.

---

