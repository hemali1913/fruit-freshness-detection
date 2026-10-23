# Fruit Freshness Detection Using Deep Learning

A beginner-friendly deep learning project that aims to classify fruit
images by their freshness condition using a Convolutional Neural Network
(CNN).

**Project status:** In progress --- dataset setup and initial
implementation are being prepared. Training results and the Streamlit
interface will be added after they are implemented and tested.

## 1. Project Overview

Fruit freshness is important for consumers, sellers, supermarkets, and
food-supply businesses. Manually checking every fruit can take time and
may lead to inconsistent decisions.

This project explores image classification to predict whether a fruit
image belongs to a fresh or rotten category. The current dataset
contains three fruit types: apples, bananas, and oranges.

## 2. Objectives

-   Organize and inspect a labelled fruit-image dataset.
-   Prepare images for deep learning.
-   Build and train a CNN image-classification model.
-   Evaluate the model using suitable metrics and visualizations.
-   Test predictions on images the model has not seen during training.
-   Develop a simple Streamlit interface for image upload and prediction
    in a later phase.

## 3. Fruit Categories

The dataset is organized into six classes:

  Folder name       Intended class
  ----------------- ----------------
  `apple`           Fresh apple
  `banana`          Fresh banana
  `orange`          Fresh orange
  `rottenapples`    Rotten apple
  `rottenbanana`    Rotten banana
  `rottenoranges`   Rotten orange

**Important:** These class meanings are based on the dataset's folder
names. The dataset will be checked before training to confirm the labels
and image counts.

## 4. Dataset

The dataset was obtained from Kaggle:

-   **Dataset name:** Fruit Freshness Dataset (Apple, Banana, Orange)
-   **Source:**
    https://www.kaggle.com/datasets/user2036/fruit-freshness-dataset-v1
-   **Content:** Images of apples, bananas, and oranges labelled by
    freshness condition.
-   **Original folders:** `Train` and `Test`
-   **Validation set:** Planned to be created from the training data
    using a validation split in code.

The dataset was downloaded and extracted locally. The exact number of
usable images will be recorded after the notebook checks the folders and
counts the supported image files. Do not assume that every file in the
downloaded archive is a valid image.

### Data split

The intended approach is to keep the supplied test set separate and use
part of the training data for validation. For example, an 80/20 split of
the original training set can be used for training and validation, if
appropriate for the dataset.

-   **Training set:** Used to learn model parameters.
-   **Validation set:** Used during development to monitor performance
    and help identify overfitting.
-   **Test set:** Kept separate for final evaluation after model
    development.

The actual split and image counts should be documented after
implementation.

## 5. Technologies

The project is planned to use:

-   **Python** --- programming language
-   **Jupyter Notebook** --- development and experimentation
-   **TensorFlow / Keras** --- image loading and CNN development
-   **NumPy** --- numerical operations
-   **Matplotlib** --- plots and visualizations
-   **Pillow** --- image handling where needed
-   **Streamlit** --- planned user interface for the final phase

The exact libraries used will be confirmed in the project's
`requirements.txt` file.

## 6. Project Workflow

1.  Download and inspect the dataset.
2.  Verify the six class folders and count images.
3.  Check for unsupported, corrupt, or misplaced files.
4.  Load images from the training and test directories.
5.  Resize images to a consistent size and scale pixel values as
    required by the model.
6.  Create a validation split from the training data.
7.  Apply suitable data augmentation to training images if needed.
8.  Define and compile a CNN model.
9.  Train the model and record training/validation accuracy and loss.
10. Plot accuracy and loss curves.
11. Evaluate the trained model on the separate test set.
12. Review predictions and relevant evaluation metrics.
13. Save the trained model.
14. Build and test a Streamlit interface for image upload and
    prediction.

Steps are a project plan; completed steps and measured results should be
updated as implementation progresses.

## 7. Suggested Folder Structure

Keep the extracted dataset folders unchanged until the notebook code has
been adjusted to match their exact names and locations.

``` text
fruite_freshness_detection/
├── dataset/
│   ├── Train/
│   │   ├── apple/
│   │   ├── banana/
│   │   ├── orange/
│   │   ├── rottenapples/
│   │   ├── rottenbanana/
│   │   └── rottenoranges/
│   └── Test/
│       ├── apple/
│       ├── banana/
│       ├── orange/
│       ├── rottenapples/
│       ├── rottenbanana/
│       └── rottenoranges/
├── Fruit_Freshness_Detection.ipynb
├── requirements.txt
├── README.md
├── saved_model/                 # created after model training
└── app.py                       # planned Streamlit application
```

Folder names are examples based on the current screenshots. Windows
paths and capitalization can differ. Update the notebook paths to match
the real folder names on your computer.

## 8. Setup

### Prerequisites

-   Python installed
-   Jupyter Notebook available
-   Dataset downloaded and extracted
-   Internet access for installing any missing packages

### Install dependencies

Open Command Prompt in the project folder and run:

``` bash
python -m pip install tensorflow numpy matplotlib pillow scikit-learn streamlit
```

If TensorFlow installation fails, check the Python version and
TensorFlow's current installation requirements. The package list can be
refined after the notebook implementation is confirmed.

### Start Jupyter Notebook

From the project folder, run:

``` bash
jupyter notebook
```

Open `Fruit_Freshness_Detection.ipynb` and execute the cells in order.
The notebook must use paths that match the actual dataset folders on the
computer.

## 9. Evaluation

The model will be evaluated using measurements such as:

-   Training accuracy and loss
-   Validation accuracy and loss
-   Test accuracy
-   Precision, recall, and F1-score, where appropriate
-   Confusion matrix
-   Example predictions

**Results are not included yet.** Add actual values and plots only after
running the notebook. Do not report estimated or invented accuracy as a
measured result.

## 10. Planned Streamlit Interface

In the final phase, a Streamlit app is planned to allow a user to:

1.  Upload a fruit image.
2.  Preview the uploaded image.
3.  Run the saved trained model on the image.
4.  View the predicted class.
5.  View a confidence score if it is correctly supported by the model
    output.

The interface will be added after model training, saving, and prediction
testing are working. A confidence score is not a guarantee that the
prediction is correct.

## 11. Current Progress and Next Steps

Current progress: - Dataset selected. - Dataset extracted locally. -
Training and testing folders inspected. - Six class folders identified
from the screenshots.

Next steps: - Confirm the exact dataset paths. - Count images in each
class and inspect a sample. - Load the data and create the validation
split. - Implement preprocessing and the initial CNN. - Train and
evaluate the model. - Add real results and screenshots to this README. -
Build and test the Streamlit interface.

Update this section as each task is completed.

## 12. Limitations

-   Predictions depend on the quality, variety, and labels of the
    dataset.
-   Lighting, camera angle, background, fruit variety, and image quality
    may affect results.
-   The model only predicts the classes it was trained on; it should not
    be assumed to recognize other fruits or diagnose food safety.
-   Performance must be measured on a separate test set before drawing
    conclusions.

## 13. Responsible Use

This is an educational project and should not be used as the only basis
for food-safety decisions. A visual prediction cannot reliably identify
every form of spoilage or determine whether a fruit is safe to eat.

## 14. License and Attribution

The dataset page lists its license and attribution conditions. Review
the Kaggle dataset's license before redistributing the images or
republishing the dataset. Credit the dataset creator and follow the
terms shown on the source page.

## 15. Author

**Project:** Fruit Freshness Detection Using Deep Learning\
**Student:** Hemali Kasad\
**Project teammate(s):** Add teammate details if required by your
college.\
**Faculty guide:** Add the guide's name as required by your college.

------------------------------------------------------------------------

*This README describes the planned project workflow. Replace planned
items with confirmed implementation details and actual experimental
results as the project progresses.*
