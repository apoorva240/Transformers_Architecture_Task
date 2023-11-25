# Movie Sentiment Analysis with Transformer Model

## Introduction

This repository contains a sentiment analysis model for movie reviews implemented using a transformer-based neural network. The model classifies reviews as either positive or negative based on user ratings.

## Dataset

The dataset used in this project is a combination of two sources: 'basics.tsv' and 'ratings.tsv'. The former contains basic information about movies, while the latter provides user ratings. The datasets are merged based on the common column 'tconst'. The focus is on movies ('titleType' is 'movie') with a substantial number of votes (more than 1000).

## Data Preprocessing

1. **Text Selection:**
   - The 'originalTitle' column is chosen as the primary text for sentiment analysis.
   - Sentiment labels ('positive' or 'negative') are assigned based on average ratings.

2. **Splitting Data:**
   - The dataset is split into training and testing sets, with 80% used for training and 20% for testing.

## Text Preprocessing

1. **Tokenization:**
   - The Keras Tokenizer is used to convert movie titles into numerical indices.

2. **Padding:**
   - Sequences are padded to a fixed length (50) to ensure uniform input size.

## Model Architecture

The neural network model consists of the following layers:

1. **Embedding Layer:**
   - Converts tokenized indices into dense vectors of fixed size (128).

2. **TransformerBlock:**
   - A custom layer representing a transformer block, incorporating multi-head self-attention and feed-forward neural networks.

3. **GlobalAveragePooling1D:**
   - Performs global average pooling over the sequence dimension.

4. **Dense Layer:**
   - A fully connected layer with a single neuron and sigmoid activation for binary sentiment prediction.

## Challenges and Solutions

- **Tokenization and Padding:**
  - Challenge: Ensuring proper tokenization and padding of sequences.
  - Solution: Utilized Keras Tokenizer and padded sequences to a fixed length.

- **Transformer Block Design:**
  - Challenge: Understanding and implementing the transformer block.
  - Solution: Designed a custom layer incorporating multi-head attention and feed-forward layers, with appropriate dropout and normalization.

## Model Training and Evaluation

- The model is compiled with the Adam optimizer and binary cross-entropy loss.
- Trained for 5 epochs on the training data, with validation on the testing set.
- Results in terms of loss and accuracy are evaluated on the test set.

## Results

After training for 5 epochs, the model achieved a certain level of accuracy on the test set, indicating its ability to generalize to unseen data.

## Future Considerations

1. **Hyperparameter Tuning:**
   - Further tuning of hyperparameters for optimal performance.

2. **Model Interpretability:**
   - Techniques to interpret and explain the decisions made by the model.

3. **Larger Datasets:**
   - Training on larger datasets for improved generalization.

## Conclusion

This repository serves as a foundation for sentiment analysis in the context of movie reviews using transformer-based neural networks. The provided code, dataset, and documentation can be extended and modified for various NLP tasks.

## Acknowledgments

Acknowledgment of libraries, frameworks, and datasets used in the project.

## References

Citations for relevant papers, documentation, or resources used during the project.

