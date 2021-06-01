# Assignment 3 - Recurrent Neural Network

### Files :
* **RNN_EngToHindi.ipynb** - Basic Training RNN model from scratch executable code with Sweep functionality
* **RNN_EngToHindi_with_Attention.ipynb** - Basic Training RNN model along with attention mechanism from scratch executable code with Sweep functionality
* **predictions_vanilla.txt** - Predictions made by normal RNN over test data.
* **predictions_Attention.txt** - Predictions made by RNN with attention mechanism over test data.
* **README.md** - Brief description about project

### Quick Run :
* Firstly execute *sweep_config* and *wandb.sweep* modules that initialize sweep with parameters and return sweep id.
* Then execute *wandb.agent* that train model with various combination of parameters.<br/>
**Note -** *It is suggested to pre-run all modules i.e. import, algorithms and supportive functionalities.*

### Key Points for Execution :
* It is a modular code in jupyter notebook format.
* One who needs to run this notebook should have a wandb login which is needed for execution of the code.
* Code is structured based on sweep functionality. There are two important sweep functions -
  * wandb.sweep - to initiate sweep with config parameters and project name and returns sweep id
  * wandb.agent - take parameters as sweep id and function name to be executed in loop with different combinations of parameters.
* It is preferred to execute all algorithm at begin as well, since sweep function randomly choose algorithms for execution.

### Part A - Train a Basic RNN model from scratch
* Used train data and validation data to train model from given Dakshina dataset.
* Training model is built after combining encoder and decoder models.
* Separate encoder and decoder models were built for future use as Inference model while prediction.
* We are using variants of RNN such as SimpleRNN, LSTM and GRU to train model.
* Following hyperparameters were used -
  * epochs : 100,50
  * no_of_hidden_layers : 1,2,3
  * hidden_layers_size : 64, 128, 256
  * regular_dropout : 0.2,0.3,0.4
  * recurrent_dropout : 0.2,0.3,0.4
  * regular_activation : 'sigmoid','tanh','relu'
  * recurrent_activation : 'sigmoid','tanh','relu'
  * cell_type : 'RNN','GRU','LSTM'
  * weight decay : 0, 1e-1, 1e-2, 1e-3,0.00099,0.00111
  * batch size : 16, 32, 64

* Word accuracy was externally calculated by prediction function using Inference model.

### Part B - Train a Basic RNN model along with Attention mechanism from scratch
* Used train data and validation data to train model from given Dakshina dataset.
* Training model is built after combining encoder and decoder models.
* Separate encoder and decoder models were built for future use as Inference model while prediction.
* Tried Bahdanau attention and Dot attention mechanism in addition with Basic RNN model.
* Also added additonal functionality of Embedding as well as Teacher forcing to the given model.
* Following hyperparameters were used -
  * epochs : 10
  * dropout : 0.5
  * no_of_hidden_layers : 1
  * hidden_layers_size : 128
  * batch size : 32
  * embedding size : 128
  * cell_type : 'GRU','LSTM'
  * attention : 'Bahdanau', 'Dot'
