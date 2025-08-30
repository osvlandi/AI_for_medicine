### Lecture Notes – 📝 Week 1 – Disease Detection with Computer Vision
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

# Training Algorithms in Radiology

-----------------------------------
        TRAINING PROCESS
-----------------------------------
- The algorithm is trained using **chest X-rays** labeled as:
   • `1 = contains condition`
   • `0 = normal`
- Goal: the algorithm learns to map an image to a probability of containing a condition.
- Common terminology: *deep learning algorithm*, *model*, *neural network*, *CNN*.

-----------------------------------
        OUTPUT & ERROR
-----------------------------------
- The algorithm outputs a **probability (score)**.
   Example:
   - Image A → 0.48 (expected label = 1 → error)
   - Image B → 0.51 (expected label = 0 → error)
- At the beginning of training, these probabilities are far from the true labels.
- The difference between predicted probability and true label is the **error**.

-----------------------------------
        LOSS FUNCTION
-----------------------------------
- To measure error, we use a **loss function**.
- In binary classification, the most common is **Binary Cross-Entropy Loss**.
- Formulas:
   • If label = 1 → `Loss = -log(P(y=1|x))`
   • If label = 0 → `Loss = -log(1 - P(y=1|x))`

### Examples
- Case 1: Label = 1, Output = 0.2 → Loss = -log(0.2) ≈ 0.70
- Case 2: Label = 0, Output = 0.7 → Loss = -log(0.3) ≈ 0.52

Over many examples, the algorithm updates itself to reduce the average loss.

-----------------------------------
   CHALLENGES IN MEDICAL DATASETS
-----------------------------------
### 1. Class Imbalance
- Real-world medical datasets have **more normal cases** than condition cases.
- Example: 100 normal vs 1 condition.
- Consequence: the model sees mostly normal images and may always predict “normal.”
- This reduces sensitivity to rare but important condition cases.

### 2. Loss Contribution
- Example: dataset with 8 images → 6 normal, 2 condition.
- If initial predictions are 0.5 for all:
   - Normal examples: `-log(1-0.5) = 0.3` → total = 1.8
   - Condition examples: `-log(0.5) = 0.3` → total = 0.6
- → The majority of the loss comes from normal examples.
- The algorithm focuses on optimizing for normals, ignoring conditions.

### 3. Weighted Loss (Solution)
- To correct imbalance, assign different weights to classes:
   - Positive class (condition): `wp = (#negative / total)`
   - Negative class (normal): `wn = (#positive / total)`
- Example: 6 normal, 2 condition
   - `wp = 6/8`, `wn = 2/8`
- With weights applied, contributions from condition and normal are balanced.
- This technique is called **weighted loss**.

-----------------------------------
        FINAL SUMMARY
-----------------------------------
- Deep learning models learn by minimizing a **loss function**.
- In medical imaging, **class imbalance** is a critical challenge.
- **Weighted loss** ensures rare cases (e.g., conditions) are not ignored.
```

