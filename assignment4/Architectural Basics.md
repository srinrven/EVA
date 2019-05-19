
                                                     Architectural Basics
                                                     
**Architectural Basics**



1. **How many layers**

   This depends on multiple factors, like 

   Receptive field of the object size in the training and validation image sets.

   Also expressivity of the problem, features in the images, some times we need more layers after edges and gradients, we add padding to make sure we have more layers and kernals before we reach the required receptive field.

   

2. **MaxPooling**

   Pooling layers in DNN are used to reduce the dimensions of data from one layer to next layer.

   Maxpooling is helps in downsampling data/information in spacial dimension.  This just not helps in reducing the dimensions/computational cost but also adds rotational invariance and translation invariance to some extent. It encapsulates the information from one layer to next with very less loss.

   One needs to find right place to introduce this in network, like based on the image sizes once 3x3 convolutions complete finding edges, gradients can be starting point.

   

3. **1x1 Convolutions**

   1x1 convolutions are used to reduce the number of channels in DNN, rather I would prefer to use combine higher number of channels into lower number of channels which are helpful in taking the required features forward in DNN.

   

4. **3x3 Convolutions**

   3x3 convolutions are image filters/matrix/mask/kernals used for feature detections like edges, gradients or any other image operations. This is preferred choice of convolution size as it can be used to used multiple times to get the effect of larger kernel size with less number of parameters. 3x3 matrices are symmetric, more intuitive for image processing. 

   

5. **Receptive Field**

6. **SoftMax**

   In mathematics, softmax is defined exponential function which takes' n' input numbers and normalizes them into 'n' probabilities. 

   In DNN lets say image category/prediction problem of K categories,  prediction layer will have different intensity for 'K' classes given an image. It is easy for prediction if the 'K' values are distributed far from each other or in other words, one final winner who is far from other 'K-1' classes. This is achieved by using softmax, as this uses exponentials 'K' values are normalized between 0 and 1 and sum of 'K' outputs of will be 1, but most important point for DNN is softmax stretches the distance between 'K' outputs. Very useful for image classifications.

   Used after last layer to clearly identify one class out of 'K' available output classes.

   But for domains where it is important to look at all 'K' outputs to make important decisions it is not preferred. 

   

7. **Learning Rate**

   Learning rate is a hyper parameter in CNN which usually small positive in the range 0.0 and 1.0. CNN in mathematical terms can be seen as a complex/challenging  optimization problem, addressed by stochastic gradient by tweaking weights such that global optima/minimum is reached. 

   In general words learning rate is the amount of weights that are updated during training. Usually LR is tuned after each epoch, for simpler problems, but it can also be turned for specific set of batches in an epoch. LR decides the rate at which the model learns. This is most important hyper parameter which decides the accuracy. There are techniques to find best learning rate for each epoch. 

   Once network architecture is finalized, one need to tune this LR parameter to improve accuracy.

   

8. **Kernels and how do we decide the number of kernels?**

   Number of kernels are not arbitrary. They can be chosen either intuitively or empirically. Depend on the task, number of kernels in each layer can change significantly. The more complex the dataset you expect networks with more kernels perform better.Intuitively, number of kernel at layer layer expected to bigger in the previous layers, as number of possible combination grow. That is why, in general, first layer kernels are less than mid- high-level ones.

   Also number of kernals depend on the expressivity and complexity of the domain, inter and intra classification in the data set. Modern architectures follow increasing of kernals with each layer (convolution block, set of convolution layers) followed by max pooling and 1x1 channel pooling, again followed by convolutions block.

9. **Batch Normalization**

   Normalize/standardize, is standard pre processing stage for CNN, for example all grey scale pixels are normalized to scale of [0 - 1].  Non normalized data makes networks to train longer, difficult and may also cause gradient explosion.

   In CNNs weights are adjusted with each input, imagine if some of the weights are much more than other weights, it will lead to above mentioned problems.  Batch normalization normalizes output from activation function before passing it next layer. In Image CNNs batch norm is nothing but channel normalization at each layer before passing the channels to next layer.

   This normalization happens per batch, so tweaking right batch size also important. Apart from normalizing BN also adds some noise (just like dropouts) to hidden layer's activation, this helps when the data distribution of training set is different from validation dataset.  
   This is used after each convolution layer except before prediction layer.

1. **Image Normalization**

2. **Position of MaxPooling**

3. **Concept of Transition Layers**

4. **Position of Transition Layer**

5. **Number of Epochs and when to increase them**

6. **DropOut**

   Dropout in DNNs is used for regularization, in another words used for preventing over fitting. 

   Dropout randomly ignores selected set of neurons, forcing other neurons to learn more finer/robust features. In each iteration different/random set of neuron are switched off.  In CNNs image augmentation is preferred approach over dropouts. Dropouts are used only in training phase but in not validation.

   Dropouts are used after in convolution layers and before transition blocks but not before prediction layer. One needs to experiment the right amount of dropout value by running network with different values, usually lies between 0.1 to 0.25.

   

7. **When do we introduce DropOut, or when do we know we have some overfitting**

8. **The distance of MaxPooling from Prediction**
Maxpooling reduces the dimension of the Chanel which is very useful in reducing parameters and improving performance. But Maxpooling should be avoided using just before prediction layers. Last layers are important for better prediction, if Maxpool is used towards end of network layer it might end up in not forwarding the features to next layers.
Ideally Maxpool to be avoided in last 3 to 4 layers before prediction. 

9. **The distance of Batch Normalization from Prediction**

10. **When do we stop convolutions and go ahead with a larger kernel or some other alternative** (which we have not yet covered)

11. **How do we know our network is not going well, comparatively, very early**

12. **Batch Size, and effects of batch size**
Batch size, is number of training samples, network/model will use in order to make update to model parameters/weights. Back propagation kicks once per batch, it will averages out the impact of all samples in a batch and  applies weights modification. So batch size place important role in time taken to get better performance. 
Optimal batch size will achieves the performance in lesser time. 

13. **When to add validation checks**

14. **LR schedule and concept behind it**

15. **Adam vs SGD**

    SGD is a variant of gradient descent. Instead of performing computations on the whole dataset — which is redundant and inefficient — SGDonly computes on a small subset or random selection of data examples. SGD produces the same performance as regular gradient descent when the learning rate is low. Stochastic gradient descent (often shortened to SGD), also known as incremental gradient descent, is an iterative method for optimizing a differentiable objective function, a stochastic approximation of gradient descent optimization. It is called stochastic because samples are selected randomly (or shuffled) instead of as a single group (as in standard gradient descent) or in the order they appear in the training set.

    The Adam optimization algorithm is an extension to stochastic gradient descent. Adam is an optimization algorithm that can used instead of the classical stochastic gradient descent procedure to update network weights iterative based in training data.
    Adam is derived from adaptive moment estimation. It is computationally efficient, little memory requirements.

    Adam is preferred over SGD.

    

16. etc (you can add more if we missed it here)



