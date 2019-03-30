# Tensorlab
A versatile deep learning tool which helps you quickly and efficiently setup experiments for time series data modelling and prediction, using Keras(with Tensorflow backend)

## Starting your first experiment
See example code in LabRunner.py to start your time series data modeling in less than 5 minutes!

Point the value of __MODLE_FOLDER__ in _Utils.py_ to a location where you want to keep all the experiment output, that folder will be used as the root fold to store all your experiment output. Once you start a new experiment, the following folder structure will be automatically created:

+-- <MODLE_FOLDER>
   | +-- 'model_id' - A simple text file containing the model/experiment ID, starting from 1
   | +-- <model_id> - The folder containing the training output of the experiment identified by the value of <model_id>
           | +-- checkpoints - The folder containing the model checkpoint files generated during the training
           | +-- snapshots - The folder containing the prediction graphs generated after each epoch, in png format
           | +-- model_fit_<model_id>.csv - The log file containing the model performance data generated after each epoch
           | +-- training_<model_id>_<timestamp>.log - The log file containing the details of the training process
           
Every time you start a new experiment, the ID in the model_id file will be automatically increased, and a new folder under with this new ID as its name will created, all training output will stored in this folder

## Resuming your existing experiment
