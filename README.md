# Real-Time-Emotion-Detection-System-for-Retail-Stores
An Emotion Detection System for Retailers to keep a track of their customers' reaction on specific products and Brands.

**Training model**
Importing OS module- to allow our code to interact with the Operating System. Imported keras – an open source neural network library which is basically written in the Python language.  From Keras, import the rest of the modules –  to enable our code to perform various functions.

**Validating model**
Now we are proceeding towards the data augmentation step, where we will use the module ImageDataGenerator
For the validation data set, only this particular normalization specification can suffice, as we do not require as many images for validation as we require to train our model.
Next, we have to take the data frame and the path of our data set into a directory and then generate or develop batches of augmented or normalized data using the above data. And to do so, the flow_from_directory method and its specifications are employed
Grayscale – because we don’t require colors to classify our emotions. The class mode is categorical as we have multiple classes . Shuffle is set to true because the model needs appropriate training.

**Incorporating Convolutional Neural Network into our model**
Moving on to neural networks, its time to employ the Conv2D, Activation, BatchNormalization, Dropout, MaxPooling2D modules under the keras.layers to train our model conveniently.
Here comes blocks of code to activate the neurons in the neural network. These are similar but the only difference is that, with each subsequent block the number of neurons doubles. This process shall start with our batch size that is 32 in #part1 and 64 in #part2 and so on until the desired number of neurons to be activated is achieved.
The model.add() method comes in use here.  3 by 3 matrices of specified neurons are being made with uniform padding throughout. ‘he_normal’ is set as it gives good variance for the distribution in terms of statistics. ‘elu’ activation – so it doesn’t have negative values and gives more accuracy. Dropout refers to the percentage of neurons to be left out or deactivated during transmission at one time. MaxPooling2D – for dimensionality reduction while BatchNormalization calculates the linear function in layers.
Specifying the ‘input_shape’ is one time job, as the subsequent part will adjust in accordance with the output of the preceding part.

**To flatten our matrices and get into the dense layer**
We use the ‘Conv’ layer for associating a feature with its neighboring features, and ‘dense’ layer for associating each feature to every other feature. ‘Flatten’ plays the role of adjusting the format to pass on to the dense layer. These connections play an important role when it comes to object detection.

**Fitting the Model with Training and Validation Data**
 In this step, we’ll try to minimize the loss or simply keep a check on it. EarlyStopping prevents overfitting and ‘reduceLRonplateau’ is for reducing the rate of learning once the model has achieved the desired accuracy.
Once these parameters have been given, we can now use callbacks to get a complete view of the internal states of our training model. This step will be followed by model.compile() as we need a loss function and optimizer for training the model.
Epoch is an important term, it determines how many times the code will iterate to achieve considerable accuracy. Lastly, declare the Final_step which employs model.fit_generator() method to work upon training our model by utilizing whatever we achieved until now.
I took epoch=48 here, so it took a couple of hours to execute.
You could take a higher value for the epoch to achieve better accuracy.
