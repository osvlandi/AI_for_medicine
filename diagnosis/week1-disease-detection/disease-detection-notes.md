### 📝 Week 1 – Disease Detection with Computer Vision
*Start of the **AI for Medicine** specialization (DeepLearning.AI, taught by Pranav Rajpurkar)*

---

#### 🔑 Key Focus
> Apply deep learning to **medical diagnosis** using medical images (X-rays, MRIs).  
> Ideal for learners who completed the ML or Deep Learning specializations.

---

### 🧪 Real-World Practice Areas
- ✅ Chest X-ray classification *(pneumonia detection)*
- ✅ Brain MRI segmentation *(tumor localization)*
- ✅ Evaluation metrics beyond accuracy:
  - Sensitivity
  - Specificity
  - AUC
- ✅ Handling imbalanced and missing data

---

### 💭 Takeaways
- **Diagnosis** = identifying disease based on symptoms, signs, and test results.
- Practical ML applications can benefit both medical and non-medical professionals.
- AI is rapidly expanding in healthcare, creating opportunities for real impact.

---

### 📚 Real-World Case Studies

#### 🧴 Dermatology – Skin Cancer Detection
- CNNs used to classify skin lesions as *cancerous or not*.
- Trained on **hundreds of thousands** of labeled images.
- Performance matched human dermatologists.
- Early detection shown to significantly improve survival outcomes.

#### 👁️ Ophthalmology – Diabetic Retinopathy (DR)
- AI model trained on **retinal fundus images**.
- Dataset: ~128,000 images — only **30%** had DR ➔ **imbalanced data**.
- Performance comparable to ophthalmologists.
- Introduced concept of **reference standard** (ground truth from expert consensus).
- Upcoming topics: methods to handle imbalanced datasets.

#### 🔬 Histopathology – Cancer Spread Detection
- Task: analyze **whole-slide tissue images** for cancer spread.
- Slides are too large for direct input ➔ broken into **high-resolution patches**.
- Patches inherit labels from the original image.
- ~270 slides used; trained on **hundreds of thousands** of patches.
- Model performance matched that of expert pathologists.
- This same **patch-based strategy** will be used in brain tumor segmentation later.

---

### 💡 Key Themes
- Deep learning can **match expert-level performance** across multiple medical domains.
- Medical imaging involves:
  - Large datasets
  - Class imbalance
  - Complex evaluation strategies
- Training, testing, and performance evaluation will be explored in depth throughout the course.

