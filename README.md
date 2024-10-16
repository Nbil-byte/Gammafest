
# Handwriting Recognition Training with MMOCR

This project uses [MMOCR](https://github.com/open-mmlab/mmocr), a toolbox for text detection and recognition, to train models for handwriting recognition. The notebook provides a step-by-step guide to preparing datasets, configuring the training pipeline, and running the model training process.

## Project Structure

The project primarily revolves around a Jupyter Notebook (`handwriting_training.ipynb`), which includes the following sections:

1. **Dataset Preparation**: Instructions for formatting annotations from [Label Studio](https://labelstud.io/) to MMOCR format.
2. **Model Training**: Code to train text detection and recognition models using the MMOCR framework.
3. **Google Colab Integration**: The notebook is designed to run in Google Colab, allowing for the use of Google Drive to store datasets and results.

## Getting Started

### Prerequisites

- Google Colab environment (optional but recommended)
- Google Drive account for storing datasets and results
- Python 3.x
- MMOCR installed (`pip install mmocr`)

### Installation

1. Clone the MMOCR repository:
   ```bash
   https://github.com/Nbil-byte/Gammafest/tree/master
   pip install -e .
   ```

2. Install additional dependencies as required by the notebook, such as:
   ```bash
   pip install label-studio
   ```

### Dataset Preparation

Ensure that your annotations from Label Studio are in a format that can be converted for use with MMOCR. The notebook contains code for this conversion.

1. Upload the dataset to Google Drive or a local directory.
2. Modify the dataset paths in the notebook to point to your dataset.

### Running the Notebook

1. Open the `handwriting_training.ipynb` notebook in Google Colab or your preferred Jupyter environment.
2. Mount your Google Drive by running the cell:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Follow the notebook steps to configure your dataset and initiate the training process.

### Configuration

To modify the model configuration, such as model architecture or training hyperparameters, refer to the configuration files provided by MMOCR. You can specify custom configurations by editing the notebook accordingly.

## Results

Once the training is complete, the model and evaluation metrics will be saved to the specified directory in your Google Drive (or local directory). You can then use the trained model for inference on new handwriting data.
