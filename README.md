DATASET
The dataset used is the CIFAR-10 dataset, which consists of 60,000 32x32 color images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images. The images are blurry(32x32 pixels only), Humans were only 94% accurate in classifying.

DATASET PREPROCESSING
We need to preprocess the dataset so the images and labels are in a form that Keras can ingest

normalize the images.
convert our class labels to one-hot vectors. This is a standard output format for neural networks(The class labels are a single integer value (0-9). What we really want is a one-hwe'll save some time by loading pre-trained weights for the All-CNN network. Using these weights, we can evaluate the performance of the All-CNN network on the testing dataset.* 16 ot vector of length ten because it is easier for CNN to output and it avoids biases to higher numbers; CNN is numerical,ex , a class value of 6 would skew the weights a lot differently than class label 1 . For example, the class label of 6 should be denoted [0, 0, 0, 0, 0, 0, 1, 0, 0, 0]. We can accomplish this using the np_utils.to_categorical() function*).
The original paper mentions that it took approximately 10 hours to train the All-CNN network for 350 epochs using a modern GPU, which is considerably faster (several orders of magnitude) than it would take to train on CPU.So I used pre-trained weights

weight_decay=1e-6 momentum=0.9 sgd;nesterov

softmax vs sigmoid

pre-trained neural networks: You are now interested in training a network to perform a new task (e.g. object detection) on a different data set (e.g. images too but not the same as the ones you used before). Instead of repeating what you did for the first network and start from training with randomly initialized weights, you can use the weights you saved from the previous network as the initial weight values for your new experiment. Initializing the weights this way is referred to as using a pre-trained network. The first network is your pre-trained network. The second one is the network you are fine-tuning. The first task used in pre-training the network can be the same as the fine-tuning stage. The datasets used for pre-training vs. fine-tuning can also be the same, but can also be different. It's really interesting to see how pre-training on a different task and different dataset can still be transferred to a new dataset and new task that are slightly different/. Using a pre-trained network generally makes sense if both tasks or both datasets have something in common.The bigger the gap, the less effective pre-training will be. It makes little sense to pre-train a network for image classification by training it on financial data first. In this case there's too much disconnect between the pre-training and fine-tuning stages.
