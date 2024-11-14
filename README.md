# Heart-Disease-Prediction--Neural-Networks-and-Hyperparameter-Tuning
This project uses neural networks to predict heart disease based on the Cleveland Clinic Foundation dataset. It explores different neural network architectures and optimizers, and utilizes hyperparameter tuning with Keras Tuner to find the optimal configuration for the model.

Project Overview

The objective of this project is to:
	1.	Build and train two different neural network architectures to classify heart disease presence.
	2.	Optimize hyperparameters using Keras Tuner for enhanced model performance.
	3.	Evaluate the models and report accuracy on a test dataset.

The dataset, provided by the Cleveland Clinic Foundation, contains multiple patient attributes and a target variable indicating the presence or absence of heart disease.
Neural Network Architectures

Model 1

	•	Input Layer: 16 neurons with sigmoid activation.
	•	Hidden Layer: 24 neurons with tanh activation.
	•	Dropout Layer: 20% dropout rate.
	•	Output Layer: Appropriate neuron count for binary classification.
	•	Optimizer: Nesterov momentum SGD with a learning rate of 0.01 and momentum of 0.9.
	•	Training: 20 epochs, batch size of 10.

Model 2

	•	Input Layer: 32 neurons with sigmoid activation.
	•	First Hidden Layer: 64 neurons with relu activation.
	•	First Dropout Layer: 30% dropout rate.
	•	Second Hidden Layer: 48 neurons with tanh activation.
	•	Second Dropout Layer: 10% dropout rate.
	•	Third Hidden Layer: 32 neurons with relu activation, L2 regularization, and random normal weight initialization.
	•	Output Layer: Appropriate neuron count for binary classification.
	•	Optimizer: Adam.
	•	Training: 25 epochs, batch size of 15.

Hyperparameter Tuning

We use the Keras Tuner to optimize the following parameters:
	•	Units in the First Hidden Dense Layer: Search range 16–256 in steps of 32 (using relu activation).
	•	Units in the Second Hidden Dense Layer: Search range 12–120 in steps of 12 (using tanh activation).
	•	Learning Rate: Search values 0.1, 0.01, 0.001, 0.0001, and 0.00001.
	•	Tuner Type: Hyperband.
	•	Early Stopping: Stop if validation loss does not improve for 3 epochs.

After tuning, the optimal hyperparameters and the number of training epochs are reported. The model is then re-trained with these settings, and final test accuracy is evaluated.

Evaluation

Each model is evaluated on a separate test set created from an 80/20 train-test split, and performance metrics are reported as:
	•	Model accuracy on the test dataset.
	•	Optimal hyperparameters and epochs for the tuned model.
