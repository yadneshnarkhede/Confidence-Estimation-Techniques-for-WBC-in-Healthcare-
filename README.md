# Confidence-Estimation-Techniques-for-WBC-in-Healthcare-
Uncertainty-aware white blood cell image classification using deep learning, temperature scaling, and softmax entropy to produce calibrated confidence scores and reduce high-risk misclassifications in medical predictions
# Confidence Estimation Techniques for WBC in Healthcare

## 📌 About This Project

This repository contains the implementation of our research work on **White Blood Cell (WBC) image classification with confidence estimation** for supporting early and reliable detection of **Acute Lymphoblastic Leukemia (ALL)** stages from microscopic blood smear images.

Unlike traditional models that only predict the class label, this system also estimates **how confident** the model is about each prediction. This makes the system more suitable for real healthcare use where incorrect high‑confidence predictions can be risky.

This project is based on our research paper published in an IEEE conference (Pune Section).

---

## 🏗️ System Architecture Diagram

"C:\Users\YADNESH\Pictures\Screenshots\Screenshot 2025-09-17 193300.png"

This diagram shows the complete pipeline of the system including image preprocessing, segmentation, CNN backbone, and confidence calibration layer.

---

## 🧪 Problem the Project Solves

Manual examination of blood smear slides:

* Is time‑consuming
* Depends heavily on expert skill
* Can lead to inconsistent results
* Requires further costly tests like flow cytometry for confirmation

This project provides an **automated, reliable, and interpretable** method to:

* Classify benign vs malignant cells
* Identify ALL subtypes (Early Pre‑B, Pre‑B, Pro‑B)
* Provide calibrated confidence scores with every prediction

---

## 🧠 Core Idea

The model answers two questions for every image:

1. *Which class does this WBC belong to?*
2. *How sure is the model about this prediction?*

This is achieved using:

* Transfer learning with lightweight CNN models
* Image segmentation to focus only on blast cells (ROI)
* Temperature scaling for probability calibration
* Softmax entropy for uncertainty measurement

---

## 🗂️ Dataset Used

* 3,242 microscopic blood smear images collected under controlled lab conditions
* Images include:

  * Benign Hematogones
  * Early Pre‑B ALL
  * Pre‑B ALL
  * Pro‑B ALL
* Images resized to **224 × 224**
* Dataset split into training, validation, and testing sets

---

## 🧹 Important Pre‑processing Steps

To improve model reliability:

* RGB → LAB color space conversion
* K‑means clustering for blast cell segmentation
* Masking to remove background noise (RBCs, plasma)
* Normalization and augmentation (flip transformations)

Segmentation ensures the model learns features **only from clinically important regions**.

---

## 🏗️ Model Architecture

Multiple pre‑trained CNNs were evaluated:

* VGG19
* ResNet50V2
* EfficientNetB0
* MobileNetV2

**MobileNetV2 / EfficientNetB0** were selected due to:

* High accuracy
* Lightweight size
* Suitability for low‑resource medical environments

Both original and segmented images are fed into the model to maximize feature learning.

---

## 📊 Performance Highlights

* ~98–99% validation accuracy with selected backbone
* Reliable generalization across unseen samples
* Reduced over‑confident wrong predictions using calibration
* Improved interpretability for clinical usage

---

## 🔍 Confidence Estimation (Key Contribution)

A post‑processing calibration step is applied:

* Temperature scaling smooths over‑confident probabilities
* Confidence scores better reflect true likelihood of correctness
* Helps in separating **confident** and **uncertain** predictions

This acts as a **safety layer** for medical AI systems.

---

## 🛠️ Tech Stack

* Python
* TensorFlow
* OpenCV
* NumPy, Pandas, Matplotlib
* Scikit‑learn
* Streamlit / Flask / Gradio (for interface in research prototype)

---

## 📄 Research Publication

This implementation is based on the paper:

**“Confidence Estimation Techniques for White Blood Cell Classification in Healthcare”**

Published in an IEEE conference (Pune Section) by authors from G H Raisoni College of Engineering and Management, Pune.

---

## 🚀 How to Run

1. Clone the repository
2. Run training script
3. Apply calibration step
4. Test model and observe confidence scores

---

## 🎯 Why This Project Matters

Most medical AI models focus only on accuracy. This project focuses on **trust, reliability, and safety** by integrating confidence estimation into WBC classification, making it more practical for real clinical support.

---

## ©️ License & Copyright

© 2026 Yadnesh Narkhede

Licensed under the MIT License. See the LICENSE file for details.

---

## 📬 Contact

For research discussion or collaboration, feel free to connect.
mail: yadnesh070504@gmail.com

