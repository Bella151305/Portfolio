***CAE model***

- For unsupervised training of **Convolutional Autoencoder (CAE)**, we use a randomly selected set of 5,000 paintings.
- The images have 24-bit color depth with varying resolutions averaged approximately at 1000 × 1000 pixels, and compressed as JPEG formatted files.
- The **goal** here is to train the CAE to **find features that are specifically useful for paintings**, which have a more specific color and composition range in comparison to real-world images.

Our **CAE** contains the following layers:
1. The input layer consists of the raw image (resampled to 256 × 256 pixels) in three channels (R, G, and B)
2. Convolutional layer of size 100 × 256 × 256 with filter size 5 × 5
3. Max-pooling layer of size 2 × 2
4. Convolutional layer of size 200 × 128 × 128 with filter size 5 × 5
5. Max-pooling layer of size 2 × 2
6. Unpooling layer of size 2 × 2
7. Deconvolutional layer of size 200 × 128 × 128 (?) with filter size 5 × 5
8. Unpooling layer of size 2 × 2
9. Deconvolutional layer of size 100 × 256 × 256 (?) with filter size 5 × 5

- The learning rate starts from 0.01 and is multiplied by 0.98 after each epoch.
- In order to further encourage the CAE to find meaningful features, we randomly remove 20% of the pixels for the images per epoch.

***CNN model***

Having trained a CAE, we can remove the decoder components and **use the CAE for initializing a supervised CNN**.

- The supervised classification benchmark consists of (3×40 =) 120 digital reproductions of paintings by Rembrandt, Renoir, and van Gough, downloaded from the Webmuseum.
- The cross entropy loss is used.

The full **CNN** contains the following layers:
1. The input layer consists of the raw image (resampled to 256 × 256 pixels) in three channels (R, G, and B)
2. Convolutional layer with 100 5 × 5 filters per input channel
3. Max-pooling layer of size 2 × 2
4. Convolutional layer with 200 5 × 5 filters per map
5. Max-pooling layer of size 2 × 2
6. Fully connected layer of size 400
7. Fully connected layer of size 200
8. Output softmax layer of size 3

- We conducted 10-fold cross validation, where in each of 10 runs 90% of the data is used for training, and 10% for validation.
- After performing 10 such training and validation runs, the average accuracy obtained for our CNN over the validation set is 96.52%.

**Experiments on improvement**

***CAE models modifications:***
- Dropout instead of custom generator
- Adam instead of learning rate scheduler
- Strided Conv instead of Pooling
- Strided Conv with normalisation only
- ELU instead of RELU
- Skip connections
- U-Net idea

***CNN models modifications:***
- Upon u-net idea
- Fully Conv idea upon unet
- Fully Conv idea upon original model
- CNN with Dropout

***Gray scaled images***
