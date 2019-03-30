# Tensorlab
A versatile deep learning tool which helps you quickly and efficiently setup experiments for time series data modelling and prediction, using Keras(with Tensorflow backend)

This tool requires basic understanding of the following concepts and frameworks
* Deep learning architeturs
 ** Time series modelling
 ** Hyperparameter tuning
* Python
 ** numpy 
 ** pandas
 ** skearn
 ** matplotlib.pyplot
* Tensorflow
* Keras

## Starting your first experiment!
See example code in LabRunner.py to start your time series data modeling in less than 5 minutes!

Point the value of __MODLE_FOLDER__ in _Utils.py_ to a location where you want to keep all the experiment output, that folder will be used as the root fold to store all your experiment output. Once you start a new experiment, the following folder structure will be automatically created:
```bash
+-- <MODLE_FOLDER>
   | +-- 'model_id' - A simple text file containing the model/experiment ID, starting from 1
   | +-- <model_id> - The folder containing the training output of the experiment identified by the value of <model_id>
           | +-- checkpoints - The folder containing the model checkpoint files generated during the training
           | +-- snapshots - The folder containing the prediction graphs generated after each epoch, in png format
           | +-- model_fit_<model_id>.csv - The log file containing the model performance data generated after each epoch
           | +-- training_<model_id>_<timestamp>.log - The log file containing the details of the training process
```           
Every time you start a new experiment, the ID in the model_id file will be automatically increased, and a new folder under with this new ID as its name will created, all training output will stored in this folder

## Resuming your existing experiment
1. Double check current model ID in model_id file, update as necessary to point it to a specific model with which you want to resume training
2. Under the target model training folder which is identified by the model ID in model_id file, retrieve the latest checkpoing ID in sub-folder checkpoints
3. Update following parameters in **LabRunner.py**
   * Set *is_resume* to True
   * Set *checkpoint_id* and *initial_epoch* of the target model's **HyperParams** object to the latest checkpoint ID
   * Run LabRunner.py to resume your experiment!
   
## Making prediction

