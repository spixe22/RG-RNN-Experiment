# RG-RNN Experiment: Relevance-Gated Recurrent Neural Network (RG-RNN) Model
[Kaggle](https://www.kaggle.com/code/ivanrazumov/rg-rnn-experiment-jena-climate-dataset)

## Introduction
This notebook presents the Relevance-Gated Recurrent Neural Network (RG-RNN) model designed for time series data. The experiment aims to evaluate the capabilities of RG-RNN in predicting temperature based on historical climate data.

## Model Description
RG-RNN is a modified architecture of recurrent neural networks (RNN) that utilizes a relevance mechanism to manage memory states. The primary idea is to adaptively update and retain the most relevant states, allowing effective handling of long sequences of data.

### How RG-RNN Works
1. **Input Data**: Time series climate data.
2. **Data Processing**: The input data is normalized and split into training, validation, and test sets.
3. **State Buffer**: The model uses a buffer to store hidden states. At each time step, the new hidden state is compared with the states in the buffer for relevance.
4. **Relevance Mechanism**: The model computes cosine similarity between the current hidden state and the states in the buffer. The least relevant state is replaced by the new hidden state.
5. **Prediction**: After processing the entire sequence, the model makes a prediction based on the last hidden state.

### Differences from GRU and LSTM
- **RG-RNN**: Uses a buffer to store and update hidden states based on their relevance to the current input state. This allows more efficient handling of long sequences, avoiding the vanishing gradient problem.
- **GRU (Gated Recurrent Unit)**: Includes two main gates (update and reset) that control which parts of the previous time step's state will be retained and which will be updated. This simplifies the architecture compared to LSTM but may be less flexible.
- **LSTM (Long Short-Term Memory)**: Contains three types of gates (input, output, and forget) that control the flow of information within the memory cell. This enables LSTM to effectively retain and retrieve information over long intervals but makes the model more complex and computationally expensive.

### Advantages of RG-RNN
- **Efficient Memory Management**: The relevance mechanism ensures that the model retains only the most important states, allowing better handling of long sequences.
- **Reduced Overfitting**: Adding noise to the training data and using a buffer helps the model avoid overfitting and improve generalization.

## Diagram
![RG-RNN Diagram](/images/rg-rnn-diagram.svg)

## Result plot
![RG-RNN Result Plot](/images/rg-rnn-result-plot.jpeg)

## Estimations
* Weights count: 1709
* R2: 0.9757375127455314
* RMSE: 1.261434

## Dataset
The dataset used in this experiment is the "Jena Climate Dataset". This dataset contains 14 features such as temperature, pressure, humidity, and wind speed, recorded at 10-minute intervals over several years. The data was collected from the Max Planck Institute for Biogeochemistry.

You can find more information about the dataset and download it from the following link:
[Jena Climate Dataset](https://www.kaggle.com/datasets/stytch16/jena-climate-2009-2016)


### References
- Max Planck Institute for Biogeochemistry. "Jena Climate Dataset."
- Kaggle: [Jena Climate Dataset on Kaggle](https://www.kaggle.com/datasets/mnassrib/jena-climate/data)


## Conclusion
This notebook presents the implementation and experimental evaluation of the RG-RNN model for the task of temperature prediction based on historical climate data. The model demonstrates high accuracy and robustness, as evidenced by the R2 and RMSE metrics on the test set.

## If you have any questions or feedback, please feel free to reach out! Cause I don't know what I'm doing. 😅
Email: spixe22@gmail.com
TG: @[spixe37](https://t.me/spixe37)