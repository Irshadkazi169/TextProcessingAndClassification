# TextProcessingAndClassification

Two quick facts up front from the EDA I ran on your test.csv:

Dataset size: 7,600 documents (rows).

Columns: 3 columns in the CSV; after re-parsing it looks like the file is the standard AG-News style with the label in column 0 and the text in column 2.

Classes: 4 classes, balanced: 1,900 documents each (labels 1..4).

Token statistics (simple whitespace tokenization): median ≈ 30 tokens, max ≈ 129 tokens → truncation to 128 tokens is appropriate.

I attempted to run full model training here, but the execution environment doesn't have TensorFlow installed (ModuleNotFoundError: No module named 'tensorflow'), so I could not train models for you in this session. Instead I prepared:

A concise EDA summary (what I found above and saved locally to /mnt/data/eda_report.json).

A full, runnable experiment notebook code (Keras/TensorFlow) you can paste into Colab or run locally — it contains:

Data loading & correct parsing of your CSV (header-less).

Preprocessing steps (tokenizer, padding/truncation to 128).

Three vocabulary sizes to test (example: 5k, 10k, 20k).

Two vocabulary modes: unedited vs edited (i.e., remove top stopwords).

Models to run: Dense (Embedding + GlobalAveragePooling), 1D CNN, RNN (Simple RNN), LSTM, Bidirectional LSTM.

Controlled hyperparameters (batch size = 100, epochs = 10 default — you can change), same optimizer (Adam), same loss (sparse categorical crossentropy).

Code to collect and save a results table (train/val/test loss & accuracy, train time).

Plotting code (training/validation loss & accuracy across epochs).

Optional code sections for using pre-trained embeddings (GloVe) and for generating a simple language model (sampling with temperature).

Below I give:

      (A) the EDA summary I produced,
      
      (B) the runnable Keras notebook script (paste into Colab and run),
      
      (C) a results table template and how to fill it,
      
      (D) short answers to the management problem and generative model idea.

