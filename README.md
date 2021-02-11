

## MNIST dataset



The MNIST database is available at http://yann.lecun.com/exdb/mnist/

The MNIST database is a dataset of handwritten digits. It has 60,000 training
samples, and 10,000 test samples. Each image is represented by 28x28 pixels, each
containing a value 0 - 255 with its grayscale value.



## Usage

mnist makes it easier to download 

To automatically use the train files, and display the first image in the
dataset, you can simply use:

```python
from keras.datasets import mnist
(X_train, y_train), (X_test, y_test) = mnist.load_data()
from matplotlib import pyplot as plt
%matplotlib inline
plt.imshow(X_train[1])
```




Images are returned as a 3D numpy array (samples * rows * columns). To train
convoluition based model, usually a 4D array is used (samples * features). To
get it, simply use:

```python

X_train = X_train.reshape(X_train.shape[0], 28, 28,1)
X_test = X_test.reshape(X_test.shape[0], 28, 28,1)
```
We use Keras sequential model to train, and use of Convolution, pooling , batchnorm and dropout layers to detect the handwritten digits from MNIST dataset


Finally we get validation accuracy of 99.40 using just 7,738 parameters, and 100 epochs.
