# Useful Resources

1. [Kernel Wiki](https://en.wikipedia.org/wiki/Kernel_(image_processing))
2. [Lode's Computer Graphics Tutorial - Image Filtering](https://lodev.org/cgtutor/filtering.html)
3. [Understanding Categorical Cross-Entropy Loss, Binary Cross-Entropy Loss, Softmax Loss, Logistic Loss, Focal Loss](https://gombru.github.io/2018/05/23/cross_entropy_loss/)
4. [RMSProp Optimizer](https://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf)
5. [Loss for Multilabel Vs Multiclass](https://stackoverflow.com/a/59433454/11105356)
6. [keras transfer learning](https://keras.io/guides/transfer_learning) [tf - transfer learning](https://www.tensorflow.org/tutorials/images/transfer_learning)
7. [Dropout](https://www.youtube.com/watch?v=ARq74QuavAo)
8. [SubwordTextEncoder](https://www.tensorflow.org/datasets/api_docs/python/tfds/deprecated/text/SubwordTextEncoder)
9. [Transformer](https://jinglescode.github.io/2020/05/27/illustrated-guide-transformer/)

## dataset
1. [tensorflow datasets](https://github.com/tensorflow/datasets/tree/master/docs/catalog)
  - [Dataset Buffer Size](https://datascience.stackexchange.com/questions/89316/tensorflows-shufflebuffer-size)

### NLP
1. [Sarcasm Detection](https://www.kaggle.com/rmisra/news-headlines-dataset-for-sarcasm-detection?select=Sarcasm_Headlines_Dataset_v2.json)
2. [BBC Articles](https://www.kaggle.com/yufengdev/bbc-fulltext-and-category)

## CNN
* Convolution is a mathematical operation on two objects to produce an outcome that expresses how the shape of one is modified by the other. With this computation, we detect a particular feature from the input image and get the result having information about that feature. This is called ‘feature map.’ 

* A first convolution layer (layers closer to the input aka bottom layers) will learn small local patterns such as edges, a second convolution layer will learn larger patterns made of the features of the first layers, and so on. This allows convnets to efficiently learn increasingly complex and abstract visual concepts (at layers closer to the output)

1. [Understanding `width_shift_range` and `height_shift_range` arguments in Keras's ImageDataGenerator class](https://stackoverflow.com/a/62487089/11105356)

* The pixels at the corner are less counted than those in the middle. This means that the pixels don’t get the same amount of weights. Additionally, If we just keep applying the convolution, we might lose the data too fast. Padding is the trick we can use here to fix this problem. As its name, padding means giving additional pixels at the boundary of the data. No padding, which is called "valid" (be default param value). Add one layer padding -> "same"
* 
Dropout advantages ->
* neighboring neurons often end up with similar weights, which can lead to overfitting, so dropping some out at random can remove this.
* often a neuron can over-weigh the input from a neuron in the previous layer, and can over specialize as a result. Thus, dropping out can break the neural network out of this potential bad habit! 

* An image is better processed by a neural network if it is in 1D form rather than 2D. In CNNs (which are popularly used for processing images), a convolution layer acts as a feature extractor which helps a fully connected layer to do the task of classifying the images. These fully connected layers use a 1D array to perform the classification. Hence we flatten the data while processing images so that 1D array operations can be performed smoothly. Rectangular or cubic shapes can’t be direct inputs. And this is why we need flattening and fully-connected layers (aka Dense layers). We flatten the output of the convolutional layers to create a **single long feature vector**. 
* [CNN clearly explained](https://towardsdatascience.com/the-most-intuitive-and-easiest-guide-for-convolutional-neural-network-3607be47480)
* ![image](https://user-images.githubusercontent.com/40615350/155012363-a032aa40-5e18-4caa-90fa-6d2cd7b67ec0.png)

## NLP
* Both `Flatten` and `GlobalAveragePooling1D/2D/3D` are valid options. So is `GlobalMaxPooling2D`. `Flatten` will result in a larger Dense layer afterwards, which is more expensive and may result in worse overfitting. But if you have lots of data, it might also perform better. For `GlobalAveragePooling` resulting shape will be (n_samples, last_axis), `Flatten()` will reshape a tensor into (n_samples, height*width*channels)
* Global Average Pooling is a pooling operation designed to replace fully connected layers in classical CNNs. The idea is to generate one feature map for each corresponding category of the classification task in the last mlpconv layer. Instead of adding fully connected layers on top of the feature maps, we take the average of each feature map, and the resulting vector is fed directly into the classification layer.
* In `Tokenizer` `num_words` parameter lets us specify the maximum number of vocabulary words to use. For example, if we set num_words=100 when initializing the Tokenizer , it will only use the 100 most frequent words in the vocabulary and filter out the remaining vocabulary words.
* Subword-based tokenization algorithm will break the sentence into subwords. The subword-based tokenization algorithms uses the following principles. 
  - Do not split the frequently used words into smaller subwords.
  - Split the rare words into smaller meaningful subwords. 
    - For instance "annoyingly" might be considered a rare word and could be decomposed into "annoying" and "ly".
* [Word, Subword, and Character-Based Tokenization](https://towardsdatascience.com/word-subword-and-character-based-tokenization-know-the-difference-ea0976b64e17)
* [HuggingFace - Tokenizer Summary](https://huggingface.co/docs/transformers/tokenizer_summary)
* sentence has 120 tokens in it, and a Conv1D with 128 filters with a Kernal size of 5 is passed over it, output shape (120 tokens + 5 -1) -> (None, 116, 128)
* When predicting words to generate texts, the more words predicted the more likely it will end up gibberish because the probability that each word matches an existing phrase goes down the more words you create
* A major drawback of word-based training for text generation instead of character-based generation because there are far more words in a typical corpus than characters, it is much more memory intensive
* In `Sequential API`, if you don't specify the `input shape` in the `Input layer` and also not in the `embedding layer`, there's no way the model can be built with the proper set of parameters. `input_length` argument is required if you are going to connect `Flatten` then `Dense` layers upstream (without it, the shape of the dense outputs cannot be computed). [input_length Embedding Layer](https://stackoverflow.com/a/61849045/11105356)
### RNN
* [RNN clearnly explained](https://towardsdatascience.com/the-most-intuitive-and-easiest-guide-for-recurrent-neural-network-873c29da73c7)

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
