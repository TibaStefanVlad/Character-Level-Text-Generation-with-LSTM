# Character-Level Text Generation with LSTM

## Overview

This project implements a character-level Recurrent Neural Network (RNN) using PyTorch to generate text. The model is trained on *Anna Karenina* by Leo Tolstoy, downloaded directly from Project Gutenberg.

The goal of the project is to learn the writing style of the novel and generate new text that resembles the original. Instead of predicting entire words, the model learns one character at a time, allowing it to produce sentences with a similar structure and vocabulary.

## Dataset

The training data consists of the complete text of *Anna Karenina*. After downloading the novel, every unique character is assigned an integer index, allowing the text to be converted into a sequence of numerical values that can be processed by the neural network.

The data is divided into batches of fixed-length sequences, where each sequence is used to predict the next character in the text.

## Model

The model is based on a two-layer LSTM network. An embedding layer is first used to convert character indices into dense vector representations. These embeddings are then processed by the LSTM, followed by a dropout layer to reduce overfitting. Finally, a fully connected layer predicts the probability of the next character in the sequence.

The network is trained using the Adam optimizer and the Cross Entropy Loss function for 20 epochs.

## Text Generation

After training, the model can generate new text by starting with a short initial string, called the *prime*. At each step, the network predicts the next character based on the characters generated so far. A `top_k` sampling strategy is used to make the generated text more natural by selecting the next character from the most likely predictions instead of always choosing the most probable one.

## Running the Project

After installing the required libraries, simply run the Python script. The program will automatically download the dataset, train the LSTM model, and generate a sample of approximately 1000 characters based on the chosen starting word.

## Technologies

This project is implemented in Python using PyTorch, NumPy, and the Requests library for downloading the dataset.

## Conclusion

This project demonstrates how recurrent neural networks can be used for character-level text generation. Although the generated text is not identical to the original novel, the model successfully learns many of the writing patterns, punctuation, and sentence structure present in the training data, producing text that resembles Leo Tolstoy's writing style.
