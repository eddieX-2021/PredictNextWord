# Next Word Prediction with LSTM and Early Stopping

This project uses an LSTM network to predict the next word in a given sequence based on Shakespeare's *Macbeth*. The model and tokenizer are created using a Jupyter Notebook (`experiments.ipynb`) and later deployed with a [Streamlit](https://streamlit.io/) web app (`app.py`).

## Files

- **experiments.ipynb**  
  Notebook for data processing, model training, and saving the trained model (`macbeth_word_predictor.h5`) along with the tokenizer (`tokenizer.pkl`).

- **app.py**  
  The Streamlit application to load the trained model and tokenizer. It accepts a sequence of words as input and predicts the next word.

- **macbeth.txt**  
  Contains the text of *Macbeth* which is used for training the model.

- **requirements.txt**  
  Lists the project dependencies.

## Installation

1. **Clone the repository or copy the project files to your local machine.**

2. **Install the dependencies.**  
   Open a terminal in the project folder and run:  
   ```cmd
   pip install -r requirements.txt
   ```

3. **(Optional) Setup a virtual environment.**  
   For example, using `venv` on Windows:  
   ```cmd
   python -m venv venv
   venv\Scripts\activate
   pip install -r requirements.txt
   ```

## Training the Model

1. Open `experiments.ipynb` using Jupyter Notebook or VS Code.
2. Run all cells to process the text, create input sequences, train the LSTM model, and save the trained model and tokenizer.
3. The notebook will produce two files:  
   - `macbeth_word_predictor.h5`
   - `tokenizer.pkl`

## Running the Streamlit App

1. Ensure that `macbeth_word_predictor.h5` and `tokenizer.pkl` are in the project folder.
2. In the terminal, run:  
   ```cmd
   streamlit run app.py
   ```
3. A new browser window/tab should open displaying the web app. You can input a word sequence and click the "Predict Next Word" button to see the result.

## How It Works

- The **experiments notebook** reads and preprocesses the text from `macbeth.txt`, tokenizes the text using Keras' `Tokenizer`, and creates n-gram sequences.  
- Sequences are padded, and labels are generated using one-hot encoding before training an LSTM model.
- The trained model is saved along with the tokenizer.
- The **Streamlit app** (`app.py`) loads the saved model and tokenizer. When a user inputs a sequence, the input is tokenized, padded, and fed into the model which then predicts the next word based on its learned patterns.

## License

This project is provided for educational purposes.
