# Handwritten Digit Recognizer

## Description

This project is a Handwritten Digit Recognizer application that uses a Convolutional Neural Network (CNN) trained on the MNIST dataset to recognize handwritten digits (0-9). The application features a graphical user interface (GUI) built with Tkinter, where users can draw digits using the mouse and get real-time predictions along with a probability distribution graph.

The CNN model is implemented using TensorFlow and Keras, achieving high accuracy on the MNIST dataset through data augmentation and regularization techniques.

## Features

- **Interactive GUI**: Draw digits directly on a canvas using the mouse.
- **Real-time Prediction**: Predict the drawn digit with confidence percentage.
- **Probability Visualization**: View a bar graph showing the probability distribution across all digits (0-9).
- **Clear and Reset**: Easily clear the canvas to draw new digits.
- **Trained Model**: Pre-trained CNN model saved in HDF5 format for quick loading.
- **Data Augmentation**: Model trained with data augmentation for better generalization.

## Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

### Steps

1. **Clone or Download the Repository**:
   - Download the project files to your local machine.

2. **Create a Virtual Environment** (Recommended):
   ```
   python -m venv venv
   venv\Scripts\activate  # On Windows
   ```

3. **Install Dependencies**:
   ```
   pip install -r requirements.txt
   ```

   The `requirements.txt` includes:
   - tensorflow
   - numpy
   - pillow
   - tk (usually comes with Python)
   - scipy
   - matplotlib

## Usage

### Running the GUI Application

1. Ensure the trained model (`mnist_cnn_model.h5`) is present in the project directory.
2. Run the GUI application:
   ```
   python gui.py
   ```
3. In the application:
   - Draw a digit (0-9) on the black canvas using the mouse.
   - Click the "Predict" button to get the prediction and view the probability graph.
   - Click the "Clear" button to reset the canvas.

### Training the Model (Optional)

If you want to retrain the model or understand the training process:

1. Run the training script:
   ```
   python model.py
   ```
2. This will:
   - Download the MNIST dataset.
   - Train a CNN model with data augmentation.
   - Save the best model as `best_mnist_model.h5` and the final model as `mnist_cnn_model.h5`.
   - Display the test accuracy.

Note: Training may take several minutes depending on your hardware.

## Project Structure

```
HDRS-graph ui/
├── gui.py                 # Main GUI application
├── model.py               # Model training script
├── requirements.txt       # Python dependencies
├── README                 # This file
└── models/
    ├── best_mnist_model.h5    # Best model checkpoint
    └── mnist_cnn_model.h5     # Final trained model
```

## Dependencies

- **TensorFlow**: For building and running the CNN model.
- **NumPy**: For numerical operations.
- **Pillow (PIL)**: For image processing.
- **Tkinter**: For the GUI (built-in with Python).
- **Matplotlib**: For plotting the probability graph.
- **SciPy**: For additional scientific computing (used by TensorFlow).

## Model Architecture

The CNN model consists of:
- Two convolutional layers with batch normalization and ReLU activation.
- Max pooling and dropout for regularization.
- A fully connected layer with 256 neurons.
- Output layer with 10 neurons (softmax for classification).

## Improvements and Notes

- **Accuracy**: The model achieves around 99% accuracy on the MNIST test set.
- **Enhancements**: For better performance, consider increasing epochs, using more advanced architectures (e.g., ResNet), or fine-tuning hyperparameters.
- **Webcam Integration**: To add webcam input, use OpenCV to capture frames, convert to grayscale, resize to 28x28, and feed into the model.
- **Deployment**: Export the model to TensorFlow SavedModel format or convert to TensorFlow Lite for mobile applications.

## Contributing

Feel free to fork the repository and submit pull requests for improvements, bug fixes, or new features.

## License

This project is open-source and available under the MIT License.