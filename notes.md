# Useful Resources

1. [Kernel Wiki](https://en.wikipedia.org/wiki/Kernel_(image_processing))
2. [Lode's Computer Graphics Tutorial - Image Filtering](https://lodev.org/cgtutor/filtering.html)
3. [Understanding Categorical Cross-Entropy Loss, Binary Cross-Entropy Loss, Softmax Loss, Logistic Loss, Focal Loss](https://gombru.github.io/2018/05/23/cross_entropy_loss/)
4. [RMSProp Optimizer](https://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf)
5. [Loss for Multilabel Vs Multiclass](https://stackoverflow.com/a/59433454/11105356)
6. [keras transfer learning](https://keras.io/guides/transfer_learning) [tf - transfer learning](https://www.tensorflow.org/tutorials/images/transfer_learning)
7. [Dropout](https://www.youtube.com/watch?v=ARq74QuavAo)

## CNN

A first convolution layer (layers closer to the input aka bottom layers) will learn small local patterns such as edges, a second convolution layer will learn larger patterns made of the features of the first layers, and so on. This allows convnets to efficiently learn increasingly complex and abstract visual concepts (at layers closer to the output)

1. [Understanding `width_shift_range` and `height_shift_range` arguments in Keras's ImageDataGenerator class](https://stackoverflow.com/a/62487089/11105356)

Dropout advantages ->
* neighboring neurons often end up with similar weights, which can lead to overfitting, so dropping some out at random can remove this.
* often a neuron can over-weigh the input from a neuron in the previous layer, and can over specialize as a result. Thus, dropping out can break the neural network out of this potential bad habit! 

## NLP
* Both `Flatten` and `GlobalAveragePooling1D/2D/3D` are valid options. So is `GlobalMaxPooling2D`. `Flatten` will result in a larger Dense layer afterwards, which is more expensive and may result in worse overfitting. But if you have lots of data, it might also perform better. For `GlobalAveragePooling` resulting shape will be (n_samples, last_axis), `Flatten()` will reshape a tensor into (n_samples, height*width*channels)

## Transfer Learning
* [Intro](https://stackoverflow.com/a/46745897/11105356)
# Code
1. [Exploring Convolutions](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C1/W3/ungraded_labs/C1_W3_Lab_2_exploring_convolutions.ipynb)
2. [CNN Intro](https://github.com/lmoroney/dlaicourse/blob/master/Course%201%20-%20Part%206%20-%20Lesson%202%20-%20Notebook.ipynb)
3. [ImageDataGenerator](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C1/W4/ungraded_labs/C1_W4_Lab_1_image_generator_no_validation.ipynb)
4. [ImageDataGenerator with Validation](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C1/W4/ungraded_labs/C1_W4_Lab_2_image_generator_with_validation.ipynb)
5. [img data processing keras](https://keras.io/api/preprocessing/image/)
6. [transfer learning intro](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C2/W3/ungraded_lab/C2_W3_Lab_1_transfer_learning.ipynb)
7. [Data Augmentation](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C2/W2/ungraded_labs/C2_W2_Lab_1_cats_v_dogs_augmentation.ipynb)
8. [multiclass img augmentation](https://github.com/https-deeplearning-ai/tensorflow-1-public/blob/main/C2/W4/ungraded_lab/C2_W4_Lab_1_multi_class_classifier.ipynb)

# Short Formula
1. Suppose an image has size W x W, the filter has size F x F, the padding is P, and the stride is S. Then the size of the resulting image of a convolution will be [(W – F + 2P) / S] + 1
2.  if our image is of size n x n, and we convolve it with an f x f filter, then the size of the resulting output is (n-f+1) x (n-f+1)
