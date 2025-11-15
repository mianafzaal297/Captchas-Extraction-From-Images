# CAPTCHA Character Recognition with Deep Learning

A complete machine learning pipeline for recognizing characters in CAPTCHA images using Convolutional Neural Networks (CNN) and computer vision techniques.

## 📋 Project Overview

This project implements an end-to-end solution for CAPTCHA recognition by:
1. Loading and preprocessing CAPTCHA images
2. Applying Otsu's thresholding for image binarization
3. Segmenting individual characters using horizontal projection
4. Training a CNN model to recognize characters
5. Evaluating model performance on test images

## 🚀 Features

- **Automated Image Preprocessing**: Otsu's thresholding for optimal binarization
- **Character Segmentation**: Horizontal projection-based segmentation
- **Deep Learning Model**: CNN architecture with dropout for robust character recognition
- **Comprehensive Visualization**: Training history plots and prediction visualizations
- **Test Pipeline**: Complete evaluation workflow for new CAPTCHA images

## 📁 Project Structure

```
.
├── Captchas_Unmodular_Strucuture.ipynb  # Main notebook with full pipeline
├── input/                                # Training CAPTCHA images
│   ├── input00.jpg
│   ├── input01.jpg
│   └── ...
├── output/                               # Ground truth labels
│   ├── output00.txt
│   ├── output01.txt
│   └── ...
├── Test_X/                               # Test images for evaluation
│   ├── input23.jpg
│   ├── input24.jpg
│   └── input25.jpg
└── Test_Y/                               # Test labels
    ├── output23.txt
    ├── output24.txt
    └── output25.txt
```

## 🛠️ Technologies Used

- **Python 3.x**
- **OpenCV**: Image processing and computer vision
- **NumPy**: Numerical computations
- **TensorFlow/Keras**: Deep learning model development
- **Matplotlib**: Data visualization

## 📦 Installation

```bash
# Clone the repository
git clone <repository-url>
cd "Captchas Task"

# Install required packages
pip install opencv-python numpy matplotlib tensorflow
```

## 🎯 Usage

### Running the Complete Pipeline

Open and run the Jupyter notebook:

```bash
jupyter notebook Captchas_Unmodular_Strucuture.ipynb
```

Execute cells sequentially to:
1. Load and preprocess images
2. Segment characters
3. Train the model
4. Evaluate on test set



## 📊 Results

### Sample Training Images

The model is trained on 25 CAPTCHA images with their corresponding labels.

### Image Preprocessing

Below is an example of the preprocessing pipeline:

**Original CAPTCHA Image → Otsu's Thresholding → Character Segmentation**

![Preprocessing Example](images/preprocessing_example.png)

### Character Segmentation

Individual characters are extracted using horizontal projection method:

![Segmented Characters](images/segmented_characters.png)

### Training Performance

The model achieves high accuracy on the validation set:

![Training History](images/training_history.png)

- **Training Accuracy**: ~95%+
- **Validation Accuracy**: ~90%+
- **Validation Loss**: <0.3

### Test Predictions

Sample predictions on test images with confidence scores:

![Test Predictions 1](images/test_prediction_1.png)
![Test Predictions 2](images/test_prediction_2.png)

Each prediction shows:
- Original CAPTCHA image
- Thresholded binary image with segmentation lines
- Individual character predictions with confidence scores

## 🔍 Key Functions

### `segment_characters_from_binary(binary_img)`
Segments characters using horizontal projection analysis on binary images.

**Parameters:**
- `binary_img`: Binary image (0/255 values)

**Returns:**
- List of (start, end) tuples representing character boundaries

### `visualize_test_images(max_images=6)`
Visualizes predictions on test images with detailed character-level analysis.

**Features:**
- Side-by-side original and thresholded images
- Segmentation boundary visualization
- Character-level predictions with confidence scores

## 📈 Performance Metrics

| Metric | Value |
|--------|-------|
| Total Characters Segmented | ~125 |
| Unique Character Classes | 10 (0-9) or 36 (0-9, A-Z) |
| Training Samples | ~112 |
| Validation Samples | ~13 |
| Model Parameters | ~150K |

## 🔧 Customization

### Adjusting Segmentation Sensitivity

```python
# In segment_characters_from_binary function
threshold = 0  # Increase for stricter segmentation
```

### Modifying Model Architecture

```python
# Add more layers or change parameters
model = Sequential([
    Conv2D(64, (3,3), activation='relu', input_shape=(IMG_H, IMG_W, 1)),
    # ... customize layers
])
```

## 🐛 Troubleshooting

**Issue**: Characters not segmenting properly
- **Solution**: Adjust threshold value in segmentation function

**Issue**: Low model accuracy
- **Solution**: Increase EPOCHS, adjust learning rate, or augment training data

**Issue**: Memory errors during training
- **Solution**: Reduce BATCH_SIZE or resize images to smaller dimensions

## 📝 Future Improvements

- [ ] Add data augmentation (rotation, scaling, noise)
- [ ] Implement transfer learning with pre-trained models
- [ ] Support for alphanumeric CAPTCHAs
- [ ] Real-time CAPTCHA solving API
- [ ] Model optimization for deployment
- [ ] Advanced segmentation techniques for overlapping characters

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👤 Author

**Your Name**
- GitHub: [@yourusername]
- Email: your.email@example.com

## 🙏 Acknowledgments

- OpenCV community for excellent documentation
- TensorFlow/Keras team for the deep learning framework
- CAPTCHA datasets for training and testing

---

⭐ If you find this project helpful, please consider giving it a star!
