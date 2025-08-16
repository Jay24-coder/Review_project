# Sentiment Analysis of Reviews

This project implements a sentiment analysis model to classify product reviews as positive or negative based on their text content. The model uses a Bidirectional LSTM neural network built with Keras and TensorFlow, processing text data from a CSV file containing reviews.

---

## Project Overview

- **Data Source**: The project uses a `Reviews.csv` file containing review summaries, text, scores, and user information.
- **Preprocessing**: 
  - Combines `Summary` and `Text` columns into a `Reviews` column.
  - Handles missing values and removes duplicates.
  - Applies tokenization and stemming using NLTK's PorterStemmer.
  - Converts text to sequences and pads them to a fixed length.
- **Model**: 
  - A Sequential Keras model with an Embedding layer, Bidirectional LSTM, and Dense output layer.
  - Trained to predict sentiment (1 for positive, 0 for negative) based on review scores.
- **Visualization**: Includes plots for training/validation loss and accuracy.

---

## Requirements

To run this project, install the required dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

The dependencies include:
- pandas
- numpy
- matplotlib
- seaborn
- nltk
- tensorflow
- keras

---

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Jay24-coder/Review_project.git
   cd Review_project
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Download NLTK Data**:
   Run the following in a Python shell to download required NLTK resources:
   ```python
   import nltk
   nltk.download('punkt')
   ```

4. **Prepare Data**:
   - Place the `Reviews.csv` file in the project directory.
   - The CSV should contain columns: `Summary`, `Text`, `Score`, `UserId`, `ProfileName`, and `Time`.

---

## Project Structure

- `main.py`: Main script containing data preprocessing, model training, and visualization code.
- `requirements.txt`: Lists Python dependencies.
- `.gitignore`: Specifies files and directories to exclude from version control.
- `README.md`: This file, providing project documentation.
- `Reviews.csv`: (Not included in repo) The dataset file with review data.

---

## Model Details

- **Input**: Tokenized and padded review text sequences (max length: 60).
- **Architecture**:
  - Embedding layer (input_dim: 20674, output_dim: 10).
  - Bidirectional LSTM layer (10 units).
  - Dense layer with sigmoid activation for binary classification.
- **Training**:
  - Optimizer: Adam (learning rate: 0.009).
  - Loss: Binary cross-entropy.
  - Metrics: Accuracy.
  - Epochs: 8.
  - Batch size: 7000.
  - Validation split: 35%.

---

## Visualizations

The script generates two plots:
- Training and validation loss over epochs.
- Training and validation accuracy over epochs.

---

## Notes

- Ensure the `Reviews.csv` file is available and properly formatted.
- The model assumes scores > 3 are positive (1) and ≤ 3 are negative (0).