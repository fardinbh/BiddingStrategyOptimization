# Bidding Strategy Optimization

## Table of Contents
- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Implementation](#implementation)
- [Model Architecture](#model-architecture)
- [Loss Function](#loss-function)
- [Hyperparameters](#hyperparameters)
- [Training](#training)
- [Evaluation](#evaluation)

## Introduction
This repository presents a solution for optimizing a trading bidding strategy using machine learning. The goal is to learn a function that maximizes trading profit while subject to a worst loss risk constraint. The solution is implemented using PyTorch and aims to tackle a non-linear optimization problem.

## Problem Statement
The problem can be formally defined as follows:

- Maximize the sum of hourly results subject to a worst loss risk constraint of $1000.
- Hourly results are calculated based on trading bid and offer volumes and prices.
- The objective is to find the optimal result on out-of-sample data.

## Dataset
We use a dataset that includes historical timeseries data with the following components:

- $X$: Engineered features, $\in \mathbb{R}^{n,5}$.
- $da$: Day ahead prices, $\in \mathbb{R}^{n, 7}$.
- $rt$: Real-time prices, $\in \mathbb{R}^{n, 7}$.

## Implementation
We implement a solution to tackle the problem as follows:

1. Load and preprocess the dataset.
2. Normalize the input data.
3. Define a PyTorch model for trading strategy optimization.
4. Create a custom loss function to evaluate the trading strategy.
5. Set hyperparameters for training.
6. Train the model on the training data.
7. Evaluate the model on the validation data.

## Model Architecture
We use a neural network model with the following architecture:

- Input layer: Number of features in the dataset.
- Hidden layer: 10 neurons.
- Output layer: 28 neurons (7 bid/offer volumes + 7 bid/offer prices).

## Loss Function
We define a custom trading loss function that considers trading volumes and prices to calculate the hourly trading profit. It also enforces the worst loss risk constraint.

## Hyperparameters
- Input size: Number of features in the dataset.
- Hidden size: Number of neurons in the hidden layer.
- Output size: 28 (7 bid/offer volumes + 7 bid/offer prices).
- Learning rate: 0.001
- Training epochs: 100

## Training
We train the model using the defined architecture, loss function, and hyperparameters. The model is trained to optimize the trading strategy to maximize profit while considering the risk constraint.

## Evaluation
We evaluate the model's performance on the validation data by calculating the mean profit and worst loss. This allows us to assess the model's ability to optimize the trading strategy.

Feel free to explore the code and adapt it to your specific trading strategy optimization problem. Make sure to have the necessary dataset in the expected format for training and evaluation.
