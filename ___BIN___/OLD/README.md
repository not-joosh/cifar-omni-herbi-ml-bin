# OPTIONS TO IMPROVE THE MODEL

source: https://medium.com/decathlondigital/improving-performance-of-image-classification-models-using-pretraining-and-a-combination-of-e271c96808d2
    Hyperparameter tuning and optimization
    Due to the nature of deep learning algorithms, we train models in two stages. First, to find the optimal hyperparameters for our model, we perform a hyperparameter optimization process. This is done using the hypertuning feature in the DecaVision library, which is inspired by the scikit-optimize library. This function starts by training a model 10 times with random combinations of hyperparameters which are predefined in the search space (i.e, hidden size, learning rate, learning rate finetune, finetune etc.). It then uses what it learned from these random combinations to find 15 better ones. In total, a single model configuration goes through 25 iterations of hyperparameter search to find the best model possible.

    Training with optimal hyperparameters
    Secondly, once we find the optimal hyperparameters, we train a new model configuration using these optimal hyperparameters. This stage starts first by training an extra layer or layers (depending on the hyperparameter optimization) on top of the frozen pretrained model, and then fine tunes few blocks of the pretrained model by unfreezing them. In all our experiments while performing hyperparameter search, we found fine tuning to return better results.
