# Mrs.Robot - Fashion Modelling &#x1F49C;

Training a **variational autoencoder** on the Fashion MNIST dataset.
  ![Google bias](https://github.com/lucylow/Mrs.Robot/blob/master/gender%20bias%20%20.png)

## How it works &#x1F49C;

Train a [variational autoenconder](https://blog.keras.io/building-autoencoders-in-keras.html) using TensorFlow.js on Node. The model will be trained on the [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset.

This example is a port of the code for a multilayer perceptron based variational
autoencoder from this link https://github.com/keras-team/keras/blob/master/examples/variational_autoencoder.py See [this tutorial](https://blog.keras.io/building-autoencoders-in-keras.html) for a description of how autoencoders work.

## Autoencoders 

 ![Autoencoders yay ](https://github.com/lucylow/Mrs.Robot/blob/master/autoencoder.jpg)
 
* Data compression algorithm where compression and decompression functions are defined for the user 
* Implemented using neural netowrks (especially useful for solving problems in unsupervised learning... but not every useful in a pragmatic sense.)

## Label Description &#x1F538;:

Labels for each training set.
* 0	T-shirt/top
* 1	Trouser
* 2	Pullover
* 3	Dress
* 4	Coat
* 5	Sandal
* 6	Shirt
* 7	Sneaker
* 8	Bag
* 9	Ankle boot

  ![Plot of subset Images from Fashion MNIST dataset](https://github.com/lucylow/Mrs.Robot/blob/master/Plot-of-a-Subset-of-Images-from-the-Fashion-MNIST-Dataset.png)


## Prepare the node environment &#x1F538;:

```sh
yarn
# Or
npm install
```

## Download the data &#x1F49C;

Download the [train-images-idx3-ubyte.gz](http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/train-images-idx3-ubyte.gz) from [this page](https://github.com/zalandoresearch/fashion-mnist#get-the-data).

Uncompress the file and put the resulting `train-images-idx3-ubyte`. Into a folder called `dataset` within this example folder.

## Run the training script &#x1F538;: 
```sh
yarn train
```

It will display a preview image after every epoch and will save the model at the end of training. At the end of each epoch the preview image should look more and more like an item of clothing. The way the loss function is written the loss at the end of a good training run will be in the 40-50 range (as opposed to more typical case of being close to zero).


### Monitoring model training with TensorBoard &#x1F49C;

By using the `--logDir` flag of the `yarn train` command, you can log the
batch-by-batch loss values to a log directory.
For example:

```sh
yarn train --logDir /tmp/vae_logs
```

Start TensorBoard  in a separate terminal:

```sh
pip install tensorboard  # Unless you've already installed tensorboard.


tensorboard --logdir /tmp/vae_logs
```

Once started, the tensorboard process will print an http:// URL to the
console. You can open it in the browser and see the loss curve, e.g, see
the example below.

![Example loss curve from training](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/vae_tensorboard.png)

## Serve the model and view the results &#x1F49C;

Once the training is complete run to serve the model and the web page that goes with it.

```sh
yarn watch
```

![screenshot of results on fashion MNIST. A 30x30 grid of small images](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/fashion-mnist-vae-scr.png)

## References &#x1F49C;
* [Tensorflow's tutorial with tf.keras, a high-level API to train Fashion MNIST] https://www.tensorflow.org/tutorials/keras/basic_classification
* [Zaiando Research Fashion MNIST data] http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/
* [Google Scholar - Publications on Fashion MNIST data sets] https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=fashion-mnist&btnG=&oq=fas
* [Building Autoencoders in Keras using DL for Python] https://blog.keras.io/building-autoencoders-in-keras.html
*
* [Kaggle Data Science competitions with fahsion data set] https://www.kaggle.com/zalando-research/fashionmnist
* Fashion-MNIST: a Novel Image Dataset for Benchmarking Machine Learning Algorithms. Han Xiao, Kashif Rasul, Roland Vollgraf. arXiv:1708.07747
