Explainable Deep Transfer Learning for Alzheimer’s Disease Classification
📌 Overview

This repository implements a deep transfer learning framework for multi-stage Alzheimer’s Disease (AD) classification using structural MRI data.

The system classifies brain scans into:

Non-Demented
Very Mild Demented
Mild Demented
Moderate Demented

The core contribution is a highly accurate + interpretable AI pipeline combining state-of-the-art CNN architectures with Grad-CAM explainability.

🎯 Objectives
Develop a multi-class AD classification model using MRI data
Benchmark multiple pretrained CNN architectures under identical conditions
Improve model interpretability using Grad-CAM
Provide a clinically relevant decision-support system
🧠 Models Used

The following pretrained CNN models (ImageNet weights) were fine-tuned:

ResNet34
EfficientNetB3
DenseNet169
MobileNetV3
InceptionV3

All models were trained using a unified experimental pipeline to ensure fair comparison.

⚙️ Methodology
📊 Dataset
Source: ADNI (via Kaggle augmented dataset)
Total Images: 33,920 MRI scans
Classes: 4 (Balanced using stratified sampling)
🔄 Data Pipeline
Data Collection
Preprocessing (Resize to 224×224, normalization)
Train/Validation/Test Split (64/16/20)
Data Augmentation (training only)
Model Training (Transfer Learning)
Grad-CAM Visualization
Evaluation
🧪 Training Configuration
Optimizer: Adam
Learning Rate: 0.0001
Loss: CrossEntropy with Label Smoothing (0.1)
Batch Size: 32
Mixed Precision (AMP)
Early Stopping (patience = 2)
📈 Results
🏆 Performance Comparison
Model	Accuracy
🥇 EfficientNetB3	99.28%
DenseNet169	99.26%
MobileNetV3	98.73%
ResNet34	98.26%
InceptionV3	96.15%

✔ Precision / Recall / F1-score ≈ 0.98 – 0.99
✔ ROC-AUC ≈ 99.7% – 99.99%

🔍 Explainability (Grad-CAM)
Visual heatmaps highlight important brain regions
Focus areas include:
Hippocampus
Cortical regions
Enhances clinical trust and interpretability
📌 Observations:
EfficientNetB3 → Best balance of accuracy + clean attention maps
DenseNet169 → Highly consistent predictions
ResNet34 → Strong but slightly diffused attention
MobileNetV3 → Lightweight but less centralized focus
InceptionV3 → Good multi-scale feature extraction
🔬 Key Contributions
📊 Systematic comparison of 5 CNN models under identical setup
🧠 Integration of deep transfer learning + explainable AI
⚖️ Balance between performance and interpretability
🏥 Designed as a clinician-support tool (not black-box AI)
📉 Reduced:
Dataset bias (stratified sampling)
Overfitting (augmentation + early stopping)
⚠️ Limitations
Single dataset dependency (ADNI-based)
Explainability is qualitative (Grad-CAM)
No clinical validation yet
Generalization across scanners remains open
🚀 Future Work
Multi-modal data integration (MRI + PET + clinical data)
Federated learning for privacy-preserving healthcare AI
Advanced explainability (SHAP, LRP, Integrated Gradients)
Clinical validation with real-world deployment
📚 Citation

If you use this work, please cite:

Mahendra J Gohil et al.,
"Explainable Deep Transfer Learning for Multi-Stage Alzheimer’s Disease Classification from Structural MRI"
📌 Conclusion

This work demonstrates that transfer learning + explainability can achieve:

Near-perfect classification accuracy (~99%)
Clinically meaningful visual explanations

It bridges the gap between high-performance AI models and real-world medical usability.
