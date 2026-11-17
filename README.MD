# Fuel Efficiency Prediction with Neural Networks

An academic machine-learning project exploring vehicle fuel-efficiency
prediction using Python, TensorFlow, and Keras.

## Objective

Predict miles per gallon (MPG) from vehicle characteristics and compare
fixed-duration training with early stopping.

## Project status

The notebook was rerun from beginning to end on November 16, 2026.

The saved outputs reproduce the original reported metrics to four

decimal places in the local environment.



This is an educational analysis, not a deployed prediction service.

## Dataset

The project uses the UCI Auto MPG dataset.

* Original records: 398
* Records after removing missing horsepower values: 392
* Development records: 314
* Held-out test records: 78

Twenty percent of the development records are reserved for validation
during model training.

The seven input features are cylinders, displacement, horsepower,
weight, acceleration, model year, and origin. MPG is the target.

Dataset: https://doi.org/10.24432/C5859H

## Methods

1. Load the dataset and inspect missing values.
2. Remove six records with missing horsepower values.
3. Create a reproducible development/test split.
4. Explore feature relationships.
5. Standardize input features using development-set statistics.
6. Train a neural network with two 64-unit ReLU hidden layers.
7. Compare 1,000-epoch training with early stopping.
8. Evaluate both models on the held-out test set.

Both models use RMSprop with a learning rate of 0.001 and mean squared
error as the training loss.

Early stopping monitors validation loss with patience of 50 epochs
and restores the best observed weights.

## Recorded coursework results

The results below were reproduced in the local rerun and are included

in the notebook's saved outputs.

|Model|Test MAE (MPG)|Test RMSE (MPG)|Training epochs|
|-|-:|-:|-:|
|Fixed-duration neural network|2.0109|2.4701|1,000|
|Early-stopping neural network|1.9439|2.5322|171|

Early stopping produced a slightly lower MAE and used fewer epochs.
The fixed-duration model produced a lower RMSE. These results do not
establish that either approach is consistently superior.

## Limitations

* Results come from one small dataset and one train/test split.
* No mean-prediction or linear-regression baseline is included.
* Normalization statistics include the validation subset, although
the test set is excluded.
* Origin is represented numerically rather than categorically.
* The historical vehicle dataset limits relevance to modern vehicles.

## Planned improvements

* Create explicit training, validation, and test partitions before
fitting preprocessing.
* Encode Origin as a categorical feature.
* Add simple baseline models.
* Examine residuals and prediction errors.
* Evaluate stability across multiple random seeds.
* Document a tested execution environment.



## Tested environment



The notebook completed a local run using Python 3.10.11 on Windows.

Direct dependency versions are recorded in requirements.txt.



Recreating the environment from this requirements file has not yet

been tested in a fresh virtual environment.



## Running the notebook

1. Create and activate a Python virtual environment.
2. Install the packages listed in requirements.txt.
3. Open fuel\_efficiency\_regression.ipynb in Jupyter or VS Code.
4. Select the virtual environment as the notebook kernel.
5. Restart the kernel and run all cells in order.

Internet access is required for the initial dataset download.


## Files

* fuel\_efficiency\_regression.ipynb — analysis, training, and evaluation
* requirements.txt — required Python packages
* .gitignore — exclusions for local and generated files

## Attribution

Prepared as academic coursework by Colter Welden.

The project follows the TensorFlow/Keras fuel-efficiency regression
tutorial workflow. The dataset and tutorial are credited below;
the project does not claim a novel model architecture.

* UCI Auto MPG: https://doi.org/10.24432/C5859H
* TensorFlow regression tutorial:
https://www.tensorflow.org/tutorials/keras/regression

