📝 Week 1 – Disease Detection with Computer Vision
Started the AI for Medicine specialization by DeepLearning.AI, taught by Pranav Rajpurkar.

🔑 Key Points:
Focus: Apply deep learning to medical diagnosis using images (X-rays, MRIs).

Ideal for those who finished the ML or Deep Learning specializations.

Real-world practice on:

Chest X-ray classification (pneumonia detection).

Brain MRI segmentation (tumor localization).

Evaluation metrics beyond accuracy (sensitivity, specificity, AUC).

Handling imbalanced and missing data.

💭 Takeaways:
Diagnosis = identifying disease from symptoms, signs, and results.

Even non-medical professionals can benefit from the practical ML lessons.

AI is growing fast in medicine — huge opportunity to make real impact.

📚 Real-world case studies:
Dermatology – Skin Cancer Detection

CNNs used to classify skin lesions as cancerous or not.

Trained on hundreds of thousands of labeled skin images.

Performance matched that of human dermatologists.

Highlighted importance of early detection in improving survival rates.

Ophthalmology – Diabetic Retinopathy (DR)

AI model trained to detect DR from retinal fundus images.

Dataset: ~128,000 images (only 30% with DR → imbalanced data).

Model performance was comparable to ophthalmologists.

Introduced concepts of reference standard (ground truth via expert consensus).

We'll later explore how to deal with imbalanced datasets.

Histopathology – Cancer Spread Analysis

Task: analyze large whole-slide tissue images to detect cancer spread.

Images too large for direct model input → split into smaller patches.

Patches inherit labels from the original image for training.

~270 slides used; trained on hundreds of thousands of patches.

Algorithms matched the performance of expert pathologists.

Same patch-based strategy will be used later for brain tumor segmentation.

💡 Key Themes:
Deep learning can match expert-level performance in multiple specialties.

Medical imaging often involves:

Large datasets

Imbalanced classes

Complex evaluation strategies

We'll explore training, testing, and evaluation procedures in-depth.
