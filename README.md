## Benchmark Using Fashion MNIST

#### [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) is the popular replacement for the handwritten digit MNIST dataset. It offers more of an accuracy challenge. Each image is an article of clothing and the goal is to correctly classify the images.

![img](results/mnist_fashion.png)

#### Most first-attempt networks on MNIST get around 90% accuracy and only take a few minutes to train. This project uses a network that will get better accuracy, but will take longer to train. It is based on the [VGG CNN](https://www.quora.com/What-is-the-VGG-neural-network) network. It uses batch normalization and [data augmentation](https://medium.com/nanonets/how-to-use-deep-learning-when-you-have-limited-data-part-2-data-augmentation-c26971dc8ced).  my benchmark.

#### The network splits the original training data into 80% training and 20% validation to check for overfitting on the training data. The model is trained for 10 epochs at a learning rate of 0.001 and then another 10 epochs at 0.0001. After those initial 20 epochs, data augmentation is added which generates new training samples by rotating, shifting, and zooming the original training samples. It is then trained for another round of epochs on this new data. This training on augmented data is the longest part of the benchmark. I wanted to test the effect of data augmentation on accuracy and performance so I made the number of epochs trained under data augmentation a user provided parameter. My test covers no augmentation, 25 augmented epochs, and 50 augmented epochs for each CUDA/instance combination. 

#### Here is a layout of my test plan.

![img](results/testplan.png)

#### Use vgg-cnn.py to run benchmarks for P2 C9 and P3 C9.
#### Use vgg-cnn-tf-1-4.py to run benchmarks for P2 C8.
#### vgg-cnn.ipynb and vgg-cnn-tf-1-4.ipynb can be used for interactive live runs of the code.

