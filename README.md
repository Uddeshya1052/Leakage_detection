# Leakage_detection using equivariant Neural Networks
1) In this project,  overall tasks are to implement, train and compare equivariant and standard network architectures for the task of leakage detection.

   Load the datasets

   leakage dataset train [m].csv

   leakage dataset validation 1000.csv

   and store the data as NumPy-Arrays

   X train, Y train 

   X validation, Y validation.

2) Train a standard fully connected neural network. Hyperparameters like number of epochs, batch size, optimizer, learning rate, depth and width of the network, activation and loss functions – all up to you. You
can use a framework like KerasTuner to optimize hyperparameters, or simple for-loops if you prefer that. Anyway, you should use the validation data in order to evaluate and compare candidate hyperparameter
configurations. Save the model as model standard [m].h5.

3) Augment the dataset. Each training example (x, y) can be complemented by seven additional virtual examples as illustrated in Figure 1. Clockwise rotations and flips on input data x are obtained as described above. A clockwise rotation on output data y is obtained through
y90 = (y2, −y1) and a flip along the vertical axis on the same data is represented by yflipped = (−y1, y2). All other operations (rotation angles and associated flips) can be computed by subsequent application
of these two operations. 

4) Repeat 2. on the augmented dataset. Save this model asmodel standard [m] augmented.h5.

5) Train an equivariant neural network on the original dataset. To that end, you need to implement a custom model using the Keras Subclassing API. All layers except the output layer must have a weight matrix that looks as follows W = [[a,b,c,b],[b,a,b,c],[c,b,a,b],[b,c,b,a]] where a, b, c are the parameters that shall be learned. Moreover, equivariant layers have no bias vectors, i.e., you have b{l} = 0. The outputlayer of an equivariant network has a weight matrix
W{L} = [[d,-d,-d,d],[-d,-d,d,d]] with only one parameter d, and no bias unit as well. Apart from these specifically structured weight matrices and the absence of bias vectors, equivariant networks look all like standard networks. However, they do not come as pre-implemented Keras layers, so you have to use the subclassing API. Once you have this, you can do anything else just as in case of the standard network. Save this model as model equivariant [m].h5.

6) Train an equivariant network on the augmented dataset. Save this model as model equivariant [m] augmented.h5.
