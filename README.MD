Fashion MNIST Classification using Neural Network

This project implements a fully connected neural network (feed-forward MLP) to classify images from the Fashion MNIST dataset into one of 10 clothing categories.
The model is trained using TensorFlow/Keras and evaluated on the standard Fashion MNIST test set.

Project Structure
fashion-mnist-classification/
│
├── fashion_classification.ipynb      # Main Colab notebook
├── README.md                         # Documentation
├── requirements.txt                  # Dependencies
│
├── results/                          # Plots and generated outputs (optional)
│   ├── training_curves.png
│   └── sample_predictions.png

Dataset

The project uses the Fashion MNIST dataset loaded via Keras:
(Reference: notebook output page 1) 

FashionClassification.ipynb - C…

60,000 training images

10,000 testing images

Image size: 28 × 28 grayscale

10 clothing categories:

T-shirt/top  
Trouser  
Pullover  
Dress  
Coat  
Sandal  
Shirt  
Sneaker  
Bag  
Ankle boot

Preprocessing



FashionClassification.ipynb - C…

Normalize pixel values:

X_train = X_train / 255.0
X_test = X_test / 255.0


Flatten 28×28 images into 784 features:

X_train = X_train.reshape(-1, 28*28)
X_test = X_test.reshape(-1, 28*28)

Model Architecture

 

FashionClassification.ipynb - C…

:

Dense(128, relu)
Dense(64, relu)
Dense(10, softmax)


Total parameters: 109,386

Loss: sparse_categorical_crossentropy

Optimizer: adam

Metric: accuracy

Training

Trained for 10 epochs with the following results (page 2) 

FashionClassification.ipynb - C…

:

Training accuracy rises from 77% → 91%

Validation accuracy rises from 85% → 88%

Loss steadily decreases across epochs

You plotted accuracy and loss curves on page 3.

Evaluation

Final model evaluation (page 2–3): 

FashionClassification.ipynb - C…

Test Accuracy: 0.88
Test Loss:     0.34


This confirms strong generalization for a simple MLP model.

Visualizations
1. Training Curves



Training vs validation accuracy curve

Training vs validation loss curve
(Reference: page 3) 

FashionClassification.ipynb - C…

Save them to:

results/training_curves.png

2. Sample Predictions



FashionClassification.ipynb - C…

.

Store this image as:

results/sample_predictions.png

How to Run
1. Clone the repo
git clone https://github.com/<username>/fashion-mnist-classification.git
cd fashion-mnist-classification

2. Install dependencies
pip install -r requirements.txt

3. Run the notebook

Open fashion_classification.ipynb in Google Colab or Jupyter Notebook.

requirements.txt
tensorflow
numpy
matplotlib
seaborn
pandas

Future Improvements

Build a CNN for higher accuracy

Add dropout and batch normalization

Use data augmentation

Compare with transfer learning on grayscale → RGB converted images

Add confusion matrix and classification report

Author

Kartik Rajesh
B.Tech CSE (AI/ML)
Google Colab • TensorFlow/Keras • Fashion MNIST
