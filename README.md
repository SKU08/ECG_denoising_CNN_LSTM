# ECG Signal Denoising and Classification

A hybrid neural network combining CNN and LSTM layers enhances ECG signal classification by capturing both spatial (waveform amplitude, shape) and temporal (event sequence) features. This approach improves feature extraction and denoising, resulting in higher classification accuracy, ideal for sequence-based tasks like ECG analysis

## Project Overview

The main components of this project are:

1. ECG Signal Denoising
2. CNN-LSTM Model for ECG Classification
3. Data Preprocessing and Loading
4. Model Training and Evaluation

## Dependencies

- PyTorch
- NumPy
- Matplotlib
- scikit-learn
- wfdb
- tqdm
- TensorBoard

## Installation

1 . Clone this repository and install the required packages:

```bash
git clone https://github.com/Milan002/ecg-denoising-classification.git
cd ecg-denoising-classification
pip install -r requirements.txt
```
2 . Download the ECG data:

Visit the MIT-BIH Arrhythmia Database: https://www.physionet.org/content/mitdb/1.0.0/
Download the database files
Place the downloaded files in a directory named ecg_data in the project root
## Usage

To run the main script:

```bash
python main_torch.py
```

This will load the ECG data, denoise it, train the CNN-LSTM model, and evaluate its performance.

## Project Structure

- `main_torch.py`: The main script that orchestrates the data loading, model creation, training, and evaluation.
- `utils.py`: Contains utility functions for data loading, preprocessing, and visualization.

## ECG Signal Denoising

We use a Hierarchical Kalman Filter (HKF) for denoising the ECG signals. This method is implemented in the `hierarchical_kalman_filter` function in `utils.py`.

## CNN-LSTM Model

The classification model is a combination of Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks. The model architecture is defined in the `CNNLSTMModel` class in `main_torch.py`.

## Data Preprocessing

The ECG data is loaded and preprocessed using functions in `utils.py`. The `get_data_set` function loads ECG records, applies denoising, and extracts relevant segments around R-peaks.

## Training and Evaluation

The model is trained using PyTorch, with the training process managed by the `train_epochs` function. The training progress is logged using TensorBoard, allowing for easy visualization of metrics.

## Results

After training, the models performance is evaluated on a test set. The results are visualized using:

1. Accuracy and loss plots (saved as `accuracy.png` and `loss.png`)
2. A confusion matrix (saved as `confusion_matrix.png`)

## Future Work

- Experiment with different denoising techniques
- Try other deep learning architectures for classification
- Incorporate more ECG leads for potentially improved accuracy

## Contributing

Contributions to this project are welcome. Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
