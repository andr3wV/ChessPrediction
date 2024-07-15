# Chess Position Evaluation Transformer

Please refer to my [ChessEngine repository](https://github.com/andr3wV/ChessEngine) to view teh Neural Network. 

## Purpose

This repository provides the implementation of a neural network model designed to rank chess positions from winning to losing. It includes a decoder-only transformer and a tokenizer. The tokenizer processes chess positions in FEN notation, and the model predicts their winning probabilities.

- **Data Source**: [Lichess Stockfish Data](https://huggingface.co/datasets/mauricett/lichess_sf)
- **Preprocessing**: Chess positions in FEN notation are evaluated in centipawns, which are then converted to winning percentages as described in the [Lichess Accuracy](https://lichess.org/page/accuracy) page. The winning percentage is binned following the method used in the [DeepMind Paper](https://arxiv.org/abs/2402.04494).

**Note**: This implementation is optimized for GPU. Running it on a CPU is not recommended.

## Setup Instructions

1. **Create a Virtual Environment and Install Prerequisites**

   ```sh
   python -m venv venv
   source venv/bin/activate   # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt

2. Download and Preprocess Data
    ```sh
    python preprocess.py

3. Train the model
    ```sh
    python train.py

## Post-Training
After training the model and saving its weights, you need to integrate it into a chess engine. Refer to my [chess-engine repository](https://github.com/andr3wV/ChessEngine) for instructions on this integration.
