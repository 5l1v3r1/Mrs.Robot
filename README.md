# Mrs.Robot Fashion Modelling &#x1F49C;

**Training a variational autoencoder on the Fashion MNIST dataset**

<div>
  
  [![Status](https://img.shields.io/badge/status-active-success.svg)]()
  [![GitHub Issues](https://img.shields.io/github/issues/lucylow/Mrs.Robot.svg)](https://github.com/lucylow/Mrs.Robot/issues)
  [![GitHub Pull Requests](https://img.shields.io/github/issues-pr/lucylow/Mrs.Robot.svg)](https://github.com/lucylow/Mrs.Robot/pulls)
  [![License](https://img.shields.io/bower/l/bootstrap)]()

</div>


---

## Table_of_Contents &#x1F49C;

* [How it works](#How_it_works-)
* [Autoencoders](#Autoencoders-)
* [Label descriptions](#Label_descriptions-)
* [Download the fashion data](#Download_the_fashion_data-)
* [Run the training script](#Run_the_training_script-) 
* [Loss error function](#Loss_error_function-)
* [TensorBoard monitoring model training](#TensorBoard_monitoring_model_training-)
* [Serve the model and view the results](#Serve_the_model_and_view_the_results-)
* [References](#references-) 

---

## How_it_works &#x1F49C;

* Train a [variational autoenconder](https://blog.keras.io/building-autoencoders-in-keras.html) using TensorFlow.js on Node
* The model will be trained on the [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset
* **Multi-layer perceptron** based variational autoencoder from [here](https://github.com/keras-team/keras/blob/master/examples/variational_autoencoder.py)

  ![Google bias](https://github.com/lucylow/Mrs.Robot/blob/master/google_search.png)

  *Image. Google Search's auto suggestions when user types in "**How to get my daughter into...**"*

---

## Autoencoders &#x1F49C;

 ![Autoencoders yay ](https://github.com/lucylow/Mrs.Robot/blob/master/autoencoder.jpg)

  *Image. How autoencoders work using the MNIST data set with the number "2"*
 
* **Data compression algorithm** with compression and decompression functions
* User defines the parameters in the function using variational autoencoder
* Implemented using **neural networks** - useful for problems in unsupervised learning


---

## Label_descriptions &#x1F49C;

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


  ![Plot of subset Images from Fashion MNIST dataset](https://github.com/lucylow/Mrs.Robot/blob/master/mnist%20labels.png)
  
  *Image. The 0 to 9 label descriptions for the Fashion MNIST dataset*
  
---
  
## Prepare_the_node_environment &#x1F49C;

```sh
yarn
# Or
npm install
```

---

## Download_the_fashion_data &#x1F49C;

* Download the fashion dataset with over 60,000 fashion training set images [train-images-idx3-ubyte.gz](http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/train-images-idx3-ubyte.gz) from [here](https://github.com/zalandoresearch/fashion-mnist#get-the-data)
* Large file size (26 MBytes) - will need to uncompress file
* Move the uncompressed file `train-images-idx3-ubyte` into `dataset` folder in the example folder of this repo

---

## Run_the_training_script &#x1F49C;

* Fashion data file is large, can't feed all the data to the model at once due to computer memory limitations. **Data is split into "batches"** 
* When all batches are fed exactly once, an "epoch" is completed. As training script runs, **preview images afer every epoch will show**
* At the end of each epoch the preview image should look more and more like an item of clothing

```sh
yarn train
```

---

## Loss_error_function &#x1F49C;

* Loss function to account for error in training
* The loss from a good training run will be approx 40-50 range. The loss from an average training run will be close to zero

![Example loss curve from training](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/vae_tensorboard.png)

  *Image of loss curve from fashion model training*


---

### TensorBoard_monitoring_model_training &#x1F49C;

Use `--logDir` flag of `yarn train` command. Log the **batch-by-batch loss values** to a log directory.

```sh
yarn train --logDir /tmp/vae_logs
```

Start TensorBoard in a separate terminal. Tensorboard process will print an http:// URL to the console and can be monitored in the browser. 

```sh
pip install tensorboard  # Unless you've already installed tensorboard.


tensorboard --logdir /tmp/vae_logs
```

---

## Serve_the_model_and_view_the_results &#x1F49C;

Once training is complete - run to serve the model and the web page that goes with it.

```sh
yarn watch
```

![screenshot of results on fashion MNIST. A 30x30 grid of small images](https://github.com/lucylow/Mrs.Robot/blob/master/fashion-mnist-vae/fashion-mnist-vae-scr.png)

  *Image of completed training results on fashion MNIST 30x30 grid of small images*

---

## References &#x1F49C;
* [Tensorflow's tutorial with tf.keras, a high-level API to train Fashion MNIST] https://www.tensorflow.org/tutorials/keras/basic_classification
* [Zaiando Research Fashion MNIST data] http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/
* [Google Scholar - Publications on Fashion MNIST data sets] https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=fashion-mnist&btnG=&oq=fas
* [Building Autoencoders in Keras using DL for Python] https://blog.keras.io/building-autoencoders-in-keras.html
* [Kaggle Data Science competitions with fahsion data set] https://www.kaggle.com/zalando-research/fashionmnist
* Fashion-MNIST: a Novel Image Dataset for Benchmarking Machine Learning Algorithms. Han Xiao, Kashif Rasul, Roland Vollgraf. arXiv:1708.07747
