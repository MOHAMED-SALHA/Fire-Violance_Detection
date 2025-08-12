# **Lung and Colon Cancer Detection Using Histopathological Images**

This repository contains the AI components for a **lung and colon cancer image classification model**. The project aims to classify histopathological images as benign or cancerous using deep learning models, including custom CNNs and transfer learning. The best-performing model is deployed via a Flask web application for real-time predictions.

---

## **Project Phases**

### **1. Data Preprocessing**

To prepare the dataset for training, we performed the following preprocessing steps:

- **Image Resizing**: All images were resized from 768x768 to **200x200 pixels** to reduce computation time while preserving critical image details.
- **Normalization**: The pixel values were normalized to a range of **[0, 1]** to maintain uniformity across the images.
- **Data Augmentation**: Various techniques such as **rotation**, **flipping**, **zoom**, and **shifting** were applied to enhance the model's generalization capability and prevent overfitting.
- **Grayscale Conversion**: We created a grayscale version of the dataset to test models with grayscale inputs alongside RGB models.

### **2. Model Development**

Several models were developed for this project, ranging from custom-built CNNs to transfer learning models:

- **Custom CNN Models**:Two custom Convolutional Neural Networks (CNNs) were developed:

  - One CNN for **grayscale images** to test performance without color information.
  - Another CNN for **RGB images**, using color data for more complex feature extraction.
- **Transfer Learning Models**:
  Pre-trained model, such as **DenseNet**, were fine-tuned on the dataset. Both grayscale and RGB versions were trained. Transfer learning allowed us to leverage pre-learned features and achieve better performance with fewer training epochs.

### **3. Model Training and Evaluation**

- **Training**: All models were trained using cross-entropy loss and the **Adam optimizer** to speed up convergence.
- **Evaluation Metrics**:
  - We evaluated the models using **accuracy**, **precision**, **recall**, and **F1-score**, providing a comprehensive view of model performance.
- **Best Performing Model**:
  - The **DenseNet model trained on RGB images** produced the best results, with the highest accuracy and strong generalization capabilities.

**Confusion matrices** were generated to analyze classification accuracy for each class and to identify areas for improvement.

### **4. Deployment**

The best-performing model was deployed using **Flask** to create an easy-to-use web interface for healthcare professionals:

- **Flask Web Application**:
  The web app allows users to upload histopathological images and receive real-time predictions on whether the tissue is benign or cancerous. The interface is designed to be simple and user-friendly.

### Results

The performance of the models was evaluated using accuracy, precision, and recall metrics. Below are the results for the various models tested:

| Model              | Accuracy | Precision | Recall |
| ------------------ | -------- | --------- | ------ |
| CNN (Gray)         | 96%      | 90%       | 99%    |
| CNN (Colored)      | 98%      | 97%       | 98%    |
| DenseNet (Gray)    | 99%      | 98%       | 99%    |
| DenseNet (Colored) | 98%      | 96%       | 97%    |

These results highlight the effectiveness of the models in classifying the input data based on the evaluated metrics.

---

## **Dataset**

**Dataset**: The model was trained using the dataset from Kaggle: [Lung and Colon Cancer Histopathological Images](https://www.kaggle.com/datasets/andrewmvd/lung-and-colon-cancer-histopathological-images).

---

## **Setup Instructions**

### **1. Clone the Repository**

```bash
$ git clone https://github.com/YourUsername/YourRepo.git
$ cd project
```

### **2. Create a Virtual Environment**

```bash
$ python3 -m venv venv
$ . venv/bin/activate
```

### **3. Install Dependencies**

```bash
$ (venv) pip install Flask keras tensorflow
```

### Run the Flask App

```python
$ (venv) python app.py
```

This will start the Flask app, allowing users to upload images and get real-time classification results.

### Future Work

- **Expanding the Dataset:** Include additional tissue types and other forms of cancer to improve model robustness.
- **Ensemble Learning:** Explore ensemble learning techniques to improve model accuracy.
- **Cloud Deployment:** Scale the deployment using platforms like AWS or Azure for broader accessibility and higher availability.

### License

This project is licensed under the MIT License.

```vbnet
This README provides a detailed description of the project phases, including data preprocessing, model development, evaluation, and deployment. It also provides instructions on how to set up and run the project and includes sections on future improvements.
```
