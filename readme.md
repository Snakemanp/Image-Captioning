# README - Deep Learning Assignment 2

## Course Details
- **Name**: Deep Learning
- **Year**: 2025
- **Semister**: 6

## Team Details
- **Team ID**: 24
- **Team Name**: Dr.Stone
- **Members**:
  - Preetham Battula
    - Roll Number: 22CS10015
    - Email: bpreetham05@gmail.com
  - Aravind Gavinikadi
    - Roll Number: 22CS10024
    - Email: agavinikadi@gmail.com
  - Kovvuru Kasyap
    - Roll Number: 22CS10039
    - Email: kasyapkovvuru@gmail.com

## Project Overview
This project implements an automatic image captioning system with robustness analysis and model identification, as per the Deep Learning Assignment 2 requirements. It consists of three parts:
- **Part A**: Custom transformer-based encoder-decoder model for captioning, benchmarked against SmolVLM.
- **Part B**: Robustness analysis under image occlusion.
- **Part C**: BERT-based classifier to distinguish model-generated captions.

## Running Instructions
1. **Environment**:
   - Open the notebooks in **Google Colab** or **Kaggle**.
   - Set the **Hardware Accelerator** to **GPU** (T4 or P100).

2. **Execution**:
   - Upload the notebook files to Colab/Kaggle.
   - Click **Run All** to execute all cells sequentially.
   - Ensure an active internet connection for downloading dependencies and data.

3. **Expected Runtime**:
   - **GPU P100**: ~7 hours total.
   - **GPU T4**: ~11–12 hours total.
   - Note: Runtime disconnection may require re-running cells (see data persistence below).

## Additional Information
- **Dataset**:
  - The dataset is downloaded from a Google Drive link provided in the assignment.
  - The zip file is unzipped automatically, populating data into folders (`/content/dataset/custom_captions_dataset/`).
  - **Note**: If the runtime disconnects, unzipped data is lost and must be re-extracted by re-running the unzip cell.

- **Part A**:
  - Implements `ImageCaptionModel` with a ViT encoder and DistilGPT2 decoder.
  - Data is loaded from `train.csv` and `test.csv`.

- **Part B**:
  - Generates occluded images (10%, 50%, 80% masking) for robustness testing.
  - Creates new directories to store occluded test samples.
  - **Note**: Occluded image data is lost on runtime disconnection and must be regenerated.

- **Part C**:
  - Uses a CSV file (`caption_classifier_dataset.csv`) for training a BERT-based `CaptionClassifier`.
  - The CSV download link is printed in the notebook output.
  - The CSV is uploaded to Google Drive and retrieved as needed.
  - **Data Persistence**: Download the CSV to retain it after runtime disconnection.
  - **Training Process**: Hyperparameter tuning selects the best configuration, followed by retraining with those parameters and evaluation on validation and test sets.

- **Dependencies**:
  - Automatically installed via `pip` commands in the notebooks (e.g., `transformers`, `rouge-score`, `evaluate`, `tqdm`).
  - Ensure internet access during the first run to install packages.

- **Outputs**:
  - All notebooks save outputs in cells (e.g., model weights, evaluation metrics).
  - Part A: Model saved as `smolvlm_custom_caption_model`.
  - Part C: Model saved as `caption_classifier_model`.
  - Check cell outputs for metrics (BLEU, ROUGE, METEOR for Parts A, B; accuracy, precision, recall, F1 for Part C).
