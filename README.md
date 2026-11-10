# Machine Learning Project -- Flower Image Classification

This is my college project for learning machine learning and deep learning with Python and PyTorch. The first milestone builds an image data pipeline and trains a small convolutional neural network (CNN) from scratch to classify flowers.

## Project progress

### Milestone 1: Data preparation and baseline CNN

The notebook currently includes:

1. Python library imports and project settings.
2. Paths to the flower dataset folders.
3. Reading the numbered class folders and collecting image paths.
4. Using `cat_to_name.json` to display flower names.
5. Resizing images and converting them to PyTorch tensors.
6. A custom PyTorch `Dataset` with `__len__` and `__getitem__`.
7. Training, validation, and held-out test `DataLoader` objects.
8. A transformed image batch visualization and tensor shape checks.
9. A basic CNN written with `torch.nn.Module`; its weights start from random initialization, with no pretrained weights.
10. Manual training and validation loops.
11. Training and validation loss and accuracy plots.
12. Validation macro F1 printed after every training epoch.
13. A separate final macro F1 evaluation on a held-out test split.
14. An overfitting sanity check using 12 training images.

## Data splits and evaluation

The dataset has numbered class folders under `train` and `valid`. The notebook creates one class-to-index mapping from the training folders and reuses it for validation.

To get a labeled test set, the notebook reserves 20% of the labeled images originally in `train`, using a stratified split so the classes keep approximately the same proportions. The model trains on the remaining 80%. The existing `valid` set is used to track performance during each epoch. The held-out test split is evaluated after training for the final result.

The dataset's original `test` folder contains unlabeled images directly in the folder. Those images are not used to calculate accuracy or F1. The held-out test set described above is separate and has labels inherited from the numbered training folders.

Macro F1 calculates an F1 score for every class and averages the class scores equally. It is included because overall accuracy can hide weak performance on less frequent classes. Accuracy and loss are also reported to help understand training progress.

## Dataset structure

The notebook expects this layout:

```text
flower_data/
└── flower_data/
    ├── train/
    │   ├── 1/
    │   ├── 2/
    │   └── ...
    ├── valid/
    │   ├── 1/
    │   ├── 2/
    │   └── ...
    ├── test/                 # unlabeled images; not used for scored evaluation
    └── cat_to_name.json
```

Update `data_path` in the notebook if the dataset is stored somewhere else on your computer.

## Technologies used

- Python
- PyTorch
- Torchvision
- scikit-learn (stratified split and macro F1 metric)
- Matplotlib
- Pillow (PIL)
- Jupyter Notebook

## How to run

1. Make sure the dataset is downloaded and extracted into the folder structure above.
2. Install the required libraries in the Python environment used by Jupyter:

   ```bash
   pip install torch torchvision scikit-learn matplotlib pillow
   ```

3. Open `milestone-1-train-valid-test-f1.ipynb` in Jupyter Notebook.
4. Check that `data_path` points to the correct `flower_data` folder.
5. Run the notebook cells from top to bottom. The old saved outputs were cleared after adding the new split, so run the cells to produce fresh metrics and plots.

The ZIP extraction cell only needs to be run when the dataset has not already been extracted. It does not need to be run every time the notebook starts.

## Current status

Milestone 1 is implemented in the notebook. The code includes data loading, a from-scratch CNN, manual training and validation, validation macro F1, a stratified held-out test split made from 20% of the training images, final held-out test evaluation, plots, and the 12-image overfit check.

Run the notebook to generate current scores. The notebook's earlier metrics were calculated before the 20% split was added and should not be presented as results for the current split.

## Author

Arun Kumar  
GitHub: [@arunAK096](https://github.com/arunAK096)
