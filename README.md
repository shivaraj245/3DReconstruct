# 📦 2D-to-3D Reconstruction Using Improved Voxel Autoencoder (IVA-128)

This repository contains the implementation of an **Improved Voxel Autoencoder (IVA-128)** capable of reconstructing 3D voxel grids from single-view 2D images. The project integrates **Attention Mechanisms**, **Deep CNN Encoding**, **3D Transposed Convolution Decoding**, and **Explainable AI (Guided Saliency)** to provide both high-quality voxel reconstruction and transparent model reasoning.

**The entire pipeline is implemented in the notebook:**  
➡️ `2d-to-3d.ipynb`  
*(Contains training, evaluation, model visualization, explainability, and results.)*

---

## 🚀 Project Highlights

### ✔ Single-View 2D → 3D Reconstruction
Reconstructs **128×128×128 voxel grids** from a single RGB image using a custom encoder–attention–decoder architecture.

### ✔ Improved Voxel Autoencoder (IVA-128)
**Key architectural components:**
- 4-stage 2D CNN Encoder
- Channel Attention Block to focus on shape-defining areas
- Large bottleneck (4096 → 2048)
- 7-stage 3D Transposed Convolution Decoder
- Sigmoid voxel occupancy prediction

### ✔ Explainable AI Integration
**Guided Saliency Maps** highlight which pixels contributed most to the 3D reconstruction.

### ✔ Dataset
Trained on **Pix3D Chairs subset**, a real-image dataset with aligned 3D shapes.

### ✔ Performance
**Best achieved metrics:**
- **IoU:** 0.2867
- **Precision:** 0.44
- **Recall:** 0.45
- **F1-score:** 0.43
- **Accuracy:** 0.95

---

## 🧠 Model Architecture (IVA-128)

```
Input 2D Image (128×128×3)
        │
        ▼
[ENCODER - 4 Conv2D Blocks]
        │
        ▼
[ATTENTION - Channel Attention Module]
        │
        ▼
[BOTTLENECK - Fully Connected (4096 → 2048)]
        │
        ▼
[DECODER - 7 ConvTranspose3D Blocks]
        │
        ▼
Output 3D Voxel Grid (128×128×128)
```

**Each Conv block contains:**
- Conv2D / Conv3DTranspose
- Batch Norm
- LeakyReLU Activation

---

## 📊 Results

### 3D Reconstruction
- Generates accurate chair geometry
- Preserves structure: backrest, legs, seat, edges
- Outputs are thresholded at 0.5 to visualize occupancy

### Explainability
**Saliency maps reveal:**
- Network focuses on chair silhouette
- High-attention on edges, corners, support legs
- Helps debug bad reconstructions

---

## 🛠️ Technologies & Skills Used

- Python, PyTorch
- CNNs, Autoencoders
- 3D Transposed Convolutions
- Voxel Representation Learning
- Explainable AI – Saliency Maps
- Computer Vision, Deep Learning
- Pix3D Dataset

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/shivaraj245/3dReconstruct.git
cd 2d-to-3d-reconstruction
```

### 2. Install dependencies
```bash
pip install torch torchvision matplotlib numpy pillow tqdm gradio
```

### 3. Open the notebook
```bash
jupyter notebook 2d-to-3d.ipynb
```

### 4. Train / test the model
Follow the notebook instructions for training and testing.

---

## 📢 Citations

If you use this repository, please cite:
- **Pix3D Dataset**
- **ShapeNet Dataset**
- **3D-R2N2 / Pix2Vox** baseline papers
- Your project paper (if published)

---

## 🙋‍♂️ Author

**Shivaraj Manikashetti**  
School of Computer Science & Engineering  
RV University, Bengaluru  
Email: shivarajm@rvu.edu.in

---

## ⭐ Acknowledgements

- Pix3D Dataset creators
- PyTorch community
- Researchers behind voxel autoencoders and 3D reconstruction architectures

---

## 📝 License

*[Add your license information here, e.g., MIT, Apache 2.0, etc.]*

---

## 🔗 Links

- **Repository:** [github.com/shivaraj245/3dReconstruct](https://github.com/shivaraj245/3dReconstruct)
- **Documentation:** [Link to docs if available]
