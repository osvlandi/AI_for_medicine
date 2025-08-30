# Lecture Notes 
# 📝 Week 1 – Disease Detection with Computer Vision

---

#### 🔑 Key Focus

> Apply deep learning to **medical diagnosis** using medical images (X-rays, MRIs).
> Ideal for learners who completed the ML or Deep Learning specializations.

---

### 🧪 Real-World Practice Areas

* ✅ Chest X-ray classification *(pneumonia detection)*
* ✅ Brain MRI segmentation *(tumor localization)*
* ✅ Evaluation metrics beyond accuracy:

  * Sensitivity
  * Specificity
  * AUC
* ✅ Handling imbalanced and missing data

---

### 💭 Takeaways

* **Diagnosis** = identifying disease based on symptoms, signs, and test results.
* Practical ML applications can benefit both medical and non-medical professionals.
* AI is rapidly expanding in healthcare, creating opportunities for real impact.

---

## 📚 Real-World Case Studies

#### 🧴 Dermatology – Skin Cancer Detection

* CNNs used to classify skin lesions as *cancerous or not*.
* Trained on **hundreds of thousands** of labeled images.
* Performance matched human dermatologists.
* Early detection shown to significantly improve survival outcomes.

#### 👁️ Ophthalmology – Diabetic Retinopathy (DR)

* AI model trained on **retinal fundus images**.
* Dataset: \~128,000 images — only **30%** had DR ➔ **imbalanced data**.
* Performance comparable to ophthalmologists.
* Introduced concept of **reference standard** (ground truth from expert consensus).
* Upcoming topics: methods to handle imbalanced datasets.

#### 🔬 Histopathology – Cancer Spread Detection

* Task: analyze **whole-slide tissue images** for cancer spread.
* Slides are too large for direct input ➔ broken into **high-resolution patches**.
* Patches inherit labels from the original image.
* \~270 slides used; trained on **hundreds of thousands** of patches.
* Model performance matched that of expert pathologists.
* This same **patch-based strategy** will be used in brain tumor segmentation later.

---

### 💡 Key Themes

* Deep learning can **match expert-level performance** across multiple medical domains.
* Medical imaging involves:

  * Large datasets
  * Class imbalance
  * Complex evaluation strategies
* Training, testing, and performance evaluation will be explored in depth throughout the course.

---

## 🏥 Training Algorithms in Radiology

### ⚙️ Training Process

* The algorithm is trained using **chest X-rays** labeled as:

  * `1 = contains condition`
  * `0 = normal`
* Goal: learn to map an image to a probability of containing a condition.
* Common terminology: *deep learning algorithm*, *model*, *neural network*, *CNN*.

---

### 📊 Output & Error

* The algorithm outputs a **probability (score)**.

  * Example:

    * Image A → 0.48 (expected 1 → error)
    * Image B → 0.51 (expected 0 → error)
* At the start of training, probabilities are far from the true labels.
* The difference between predicted probability and true label = **error**.

---

### 🔢 Loss Function

* Error is measured using a **loss function**.
* In binary classification, the most common is **Binary Cross-Entropy Loss**.
* Formulas:

  * Label = 1 → `Loss = -log(P(y=1|x))`
  * Label = 0 → `Loss = -log(1 - P(y=1|x))`

#### Examples

* Label = 1, Output = 0.2 → Loss ≈ 0.70
* Label = 0, Output = 0.7 → Loss ≈ 0.52

> Over many examples, the algorithm updates itself to reduce the **average loss**.

---

### ⚠️ Challenges in Medical Datasets

#### 1. Class Imbalance

* Medical datasets usually contain **more normal cases** than condition cases.
* Example: 100 normal vs 1 condition.
* Consequence: model predicts mostly “normal,” missing rare but critical cases.

#### 2. Loss Contribution

* Example: 8 images → 6 normal, 2 condition.
* If initial predictions = 0.5 for all:

  * Normal → `-log(1-0.5) = 0.3` × 6 = **1.8**
  * Condition → `-log(0.5) = 0.3` × 2 = **0.6**
* Result: Loss dominated by normal examples → model ignores conditions.

#### 3. Weighted Loss (Solution)

* Assign different weights to balance contributions:

  * Positive class (condition): `wp = (#negative / total)`
  * Negative class (normal): `wn = (#positive / total)`
* Example: 6 normal, 2 condition

  * `wp = 6/8`, `wn = 2/8`
* Result: contributions from both classes are balanced.
* Known as **weighted loss**.

---

### ✅ Final Summary

* Deep learning models learn by minimizing a **loss function**.
* In medical imaging, **class imbalance** is a major challenge.
* **Weighted loss** helps ensure rare but important conditions are not ignored.
