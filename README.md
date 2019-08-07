# Mrs.Robot Fashion Modelling &#x1F49C;

Training a **variational autoencoder** on the Fashion MNIST dataset.
  ![Google bias](https://github.com/lucylow/Mrs.Robot/blob/master/gender%20bias%20%20.png)

(Image of Google Search's auto suggestions when user types in "How to get my daughter into...")

## How it works &#x1F49C;

* Train a [variational autoenconder](https://blog.keras.io/building-autoencoders-in-keras.html) using TensorFlow.js on Node
* The model will be trained on the [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset
* Multilayer perceptron based variational autoencoder from [here](https://github.com/keras-team/keras/blob/master/examples/variational_autoencoder.py )


## Autoencoders 

 ![Autoencoders yay ](https://github.com/lucylow/Mrs.Robot/blob/master/autoencoder.jpg)

(Image of how autoencoders work using the MNIST data set with the number "2")
 
* **Data compression algorithm** with compression and decompression functions
* User defines the parameters in the function using variational autoencoder
* Implemented using **neural networks** - useful for problems in unsupervised learning

## Label Descriptions  &#x1F538;
0.	T-shirt/top
1.	Trouser
2.	Pullover
3.	Dress
4.	Coat
5.	Sandal
6.	Shirt
7.	Sneaker
8.	Bag
9.	Ankle boot
  ![Plot of subset Images from Fashion MNIST dataset](https://github.com/lucylow/Mrs.Robot/blob/master/Plot-of-a-Subset-of-Images-from-the-Fashion-MNIST-Dataset.png)
  (Image of the 0 to 9 label descriptions for the Fashion MNIST dataset)
## Prepare the node environment &#x1F538;:

```sh
yarn
# Or
npm install
```

## Download the fashion data &#x1F49C;

* Download the fashion dataset [train-images-idx3-ubyte.gz](http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/train-images-idx3-ubyte.gz) from [this page](https://github.com/zalandoresearch/fashion-mnist#get-the-data).

* Dataset has **60,000 fashion training set images** 
* Large file size (26 MBytes) so you will need to uncompress the file
* Move the uncompressed file `train-images-idx3-ubyte` into `dataset` folder in the example folder of this repo

## Run the training script &#x1F538;: 
```sh
yarn train
```

* Model is saved after the end of training
* Fashion data file is large, we can't feed all the data to the model at once due to limitations in computer memory. Data is split into **"batches"** which can fit into computer memory at once
* When all batches are fed exactly once, we complete an "epoch". As training script runs, **preview images afer every epoch** will show. At the end of each epoch the preview image should look more and more like an item of clothing. 
* **Loss function accounts for error**. The loss from a good training run will be approx 40-50 range. The loss from an average training run will be close to zero.


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

Once started, the tensorboard process will print an http:// URL to the console. Open in browser and see the loss curve:
![Example loss curve from training](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/vae_tensorboard.png)

(Image of loss curve from fashion model training)

## Serve the model and view the results &#x1F49C;

Once the training is complete run to serve the model and the web page that goes with it.

```sh
yarn watch
```

![screenshot of results on fashion MNIST. A 30x30 grid of small images](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/fashion-mnist-vae-scr.png)
(Image of completed training results on fashion MNIST via 30x30 grid of small images)

## References &#x1F49C;
* [Tensorflow's tutorial with tf.keras, a high-level API to train Fashion MNIST] https://www.tensorflow.org/tutorials/keras/basic_classification
* [Zaiando Research Fashion MNIST data] http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/
* [Google Scholar - Publications on Fashion MNIST data sets] https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=fashion-mnist&btnG=&oq=fas
* [Building Autoencoders in Keras using DL for Python] https://blog.keras.io/building-autoencoders-in-keras.html
* [Kaggle Data Science competitions with fahsion data set] https://www.kaggle.com/zalando-research/fashionmnist
* Fashion-MNIST: a Novel Image Dataset for Benchmarking Machine Learning Algorithms. Han Xiao, Kashif Rasul, Roland Vollgraf. arXiv:1708.07747
