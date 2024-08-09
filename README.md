# Image Captioning Project

## Overview

This project focuses on generating descriptive captions for images using a combination of word embeddings, Long Short-Term Memory (LSTM) networks, and Convolutional Neural Networks (CNNs). 
The model integrates CNNs for image feature extraction, embeddings for text processing, and LSTMs for sequential prediction, ultimately enabling the generation of captions that accurately describe the content of images.

## Architecture

### 1. CNN for Feature Extraction
- **Pre-trained Model**: ResNet18 was used as the CNN architecture.
- **Functionality**: The CNN extracts high-level features from the images, providing a fixed-size vector representation for each image. These features serve as the initial input to the LSTM for caption generation.

### 2. Word Embedding
- **Technique**: Pre-trained word embeddings are used to convert words into dense vectors of fixed size, capturing semantic meaning.
- **Application**: Each word in the caption is converted into an embedding vector before being fed into the LSTM network.

### 3. LSTM for Caption Generation
- **Model**: A two-layer LSTM with 256 hidden units was implemented.
- **Input**: The LSTM receives image features (from CNN) and word embeddings sequentially to predict the next word in the caption.
- **Output**: The final output is a sequence of words that form a caption, generated word by word until an end token (`<EOS>`) is predicted.

## Dataset

- **Training Data**: The model was trained using a dataset comprising images and their corresponding captions. Each image is associated with multiple captions, providing diverse descriptive information.
- **Data Processing**: 
  - The images were preprocessed to a uniform size.
  - Captions were tokenized, padded, and indexed.
  - The dataset was divided into training and validation sets.

## Training

- **Optimizer**: Adam optimizer was used for training with a learning rate set based on experimentation.
- **Loss Function**: Cross-entropy loss was employed to evaluate the discrepancy between the predicted and actual captions.
- **Training Strategy**: The model was trained in mini-batches with the goal of minimizing the loss over multiple epochs.
