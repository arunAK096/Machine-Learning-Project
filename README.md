# Machine Learning Project -- Flower Image Classification

This is my college project for learning Machine Learning and Deep
Learning using Python and PyTorch.

In this project, I am building a flower image classification system step
by step. The first milestone focuses on preparing the image data and
creating a basic Convolutional Neural Network (CNN).

## Project Progress

### Milestone 1: Data Preparation and Basic CNN

In this milestone, I have worked on:

1.  Importing the required Python libraries.
2.  Setting the dataset folder paths and project settings.
3.  Reading flower class folders and collecting image paths.
4.  Mapping flower class IDs to labels using `cat_to_name.json`.
5.  Resizing images and converting them into PyTorch tensors.
6.  Creating a custom PyTorch `Dataset`.
7.  Creating `DataLoader` objects for training and validation.
8.  Building a basic CNN model from scratch.
9.  Setting up model training and validation.
10. Plotting training loss and accuracy.
11. Performing a small overfitting check using a subset of 12 training
    images.

## Technologies Used

-   Python
-   PyTorch
-   Torchvision
-   NumPy
-   Matplotlib
-   Pillow (PIL)
-   Jupyter Notebook

## Dataset Structure

The notebook expects the flower dataset to be arranged like this:

``` text
flower_data/
└── flower_data/
    ├── train/
    ├── valid/
    ├── test/
    └── cat_to_name.json
```

The `train` and `valid` folders contain images organised by class. The
`test` folder is used for test images, which may not have labels.

**Note:** Update the dataset path in the notebook to match the location
on your computer.

## How to Run

1.  Clone or download this repository.

2.  Make sure Python and Jupyter Notebook are installed.

3.  Install the required libraries:

    ``` bash
    pip install torch torchvision matplotlib pillow numpy
    ```

4.  Download and extract the flower dataset into the expected folder
    structure.

5.  Open `milestone-1.ipynb` in Jupyter Notebook.

6.  Update `data_path` in the notebook to point to your dataset folder.

7.  Run the notebook cells from top to bottom.

## Current Status

This repository is a work in progress. The notebook contains the first
milestone: data preparation, a basic CNN, training and validation code,
progress plots, and a small sanity check. I will add further
improvements and results as the project develops.

## Author

Arun Kumar\
GitHub: [@arunAK096](https://github.com/arunAK096)
