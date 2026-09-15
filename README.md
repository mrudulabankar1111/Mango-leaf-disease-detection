# Mango-leaf-disease-detection
CNN-based detection and classification of mango leaf diseases using image processing.
#Mango Leaf Disease Detection

Automated detection and classification of mango leaf diseases using deep learning (CNN / transfer learning), built to help farmers move from slow manual inspection to fast, reliable, AI-based diagnosis.

>Overview

Mango is one of the most economically important fruit crops worldwide, but its productivity is heavily threatened by leaf diseases such as anthracnose, bacterial canker, powdery mildew, and more. Manual inspection is time-consuming, subjective, and impractical at scale.

This project uses a Convolutional Neural Network (CNN), built with transfer learning on MobileNetV2, to automatically classify mango leaf images into 8 categories — 7 disease classes plus healthy — enabling rapid, scalable, and low-cost disease detection for precision agriculture.

>Disease Classes

The model classifies leaves into the following 8 categories:

>Class	Cause	Description
-Healthy Leaf	—	Symptom-free, green, glossy leaves
-Anthracnose	Colletotrichum gloeosporioides (fungal)	Dark brown to black irregular lesions
-Bacterial Canker	Xanthomonas campestris	Water-soaked spots with a yellow halo
-Powdery Mildew	Oidium mangiferae (fungal)	White powdery growth on young leaves
-Sooty Mould	Fungal (grows on insect honeydew)	Black, velvety coating reducing photosynthesis
-Die Back	Botryodiplodia theobromae	Tip drying and necrosis along the midrib
-Gall Midge	Insect larvae	Swollen/distorted leaf tissue
-Leaf Cutting Weevil	Insect damage	Semicircular cuts along leaf edges
>Dataset
Source: Mango Leaf Disease Dataset on Kaggle
Size: 4,000 images total — 500 images per class across 8 balanced classes
Split: 80% training / 20% validation

The dataset is not included in this repository due to size. Download it from the Kaggle and place it according to the folder structure expected in the notebook.
 >Methodology
-Data Preprocessing — resizing, normalization, and augmentation (rotation, flipping, zoom, shifting) to improve robustness and reduce overfitting.
-Model Design — transfer learning using MobileNetV2 (pretrained on ImageNet) as the base, with frozen base layers and a custom classification head:
-Global Average Pooling
-Dropout (to reduce overfitting)
-Dense layer with softmax activation
-Training — Adam optimizer (learning rate = 1e-4), categorical cross-entropy loss, trained for 10–15 epochs with early stopping, checkpointing, and learning rate reduction. Optional fine-tuning by unfreezing deeper MobileNetV2 layers.
-Evaluation — Accuracy, Precision, Recall, and F1-score computed on the validation set.
-Deployment — an interactive demo interface built with Gradio, hosted inside Google Colab, letting users upload a leaf image and get real-time predictions with confidence scores.
 >Results

The model achieves high classification accuracy across disease categories, with confidence scores frequently exceeding 90–99% on clear disease presentations. Example predictions:

Case	Predicted Class	Confidence
Case I	Bacterial Canker	98.84%
Case II	Healthy	100%
Case III	Anthracnose	71.46%
Tech Stack
Python
TensorFlow / Keras (MobileNetV2 transfer learning)
Google Colab
Gradio (deployment interface)
OpenCV (image preprocessing)
Getting Started
Clone this repository:
bash
   git clone https://github.com/mrudulabankar1111/Mango-leaf-disease-detection.git
Open the notebook in Google Colab (badge link inside the notebook file).
Download the dataset from Kaggle and mount it in your Colab environment (e.g., via Google Drive).
Run the notebook cells in order: data preprocessing → model training → evaluation → Gradio demo.
 Project Structure
- notebook.ipynb        # Training and evaluation notebook (Colab)
- README.md
- .gitignore
 References

Key references and prior work that informed this project are listed in the full project report and paper (included/linked separately).

