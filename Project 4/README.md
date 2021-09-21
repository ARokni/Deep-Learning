# Fourth Project
* In this project, I have implemented an `Image-Captioning` task utilizing `CNN` and `LSTM`  on `Flickr8k` dataset.

* **Dataset**: Flickr8k consist of two different part: **Images** and **Captions**. The dataset contains 8092 images with different sizes, and there are 5 captions for each image. 
    
* **Preprocess**: 
    * **Images**
        - First, due to the varied sizes of images, I have utilized a transformation to resize all images to a specified shape.
        - Second, I applied a random crop on each image for `Data Augmentation` issue.
        - In the end, I normalized all the images in order to cope the problems of uneven large-scale fatures.
    * **Captions**
        -   First, I have loaded the captions into a dataframe, and then I  lower cased all the letters and eliminated all punctuations and irrelevant characters from the captions.
        - second, constructed  a `Vocabulary` based on the captions.
        - In the end, I have utilized **`Padding`** to have sentences with same length at each batch of the data. 
    
* **Network's Model** 
    - I have applied a **Hybrid** LSTM and CNN architecture: the CNN part extracts the features of a given image, then the LSTM part utilize the features in order to provide a meaningful sentence that describes the image. 
    -  For the CNN part I have applied a pretrained `Resnet18`. The last layer of the resnet is replaced with a linear layer in order to provide the required features of an image.
    - For the LSTM I utilized the LSTM module that is available in PyTorch. The output of the LSTM is given to a linear layer that convert the output of the LSTM to a vector with the **vocabulary** size dimension.
    - Afther the model was trained  I implemented a function to caption the test images. This function is provided in my notbook with **caption_prediction**.
    
* In **Part 1**, all layers of  **Resnet18** except the last linear layer has been freezed in the training process. `Cross Entropy` and `Adam` are utilized as loss function and optimzer. The hyperparameters has been determined by means of search and trail. The codes and results are provided in [Deep_ImageCaptioning_part1.ipynb]().

* In **Part 2**, in contrast to **Part 1**, all layers of **Resnet18** trained with the rest of the model. All other conditions are the same as **Part 1**. The codes and results are provided in [Deep_ImageCaptioning_part2.ipynb]().

* In **Part B**, the architecture of **Part A** has been enriched with `Batch-Normalization (BN)` layers. On the ground of [[3]](#3), I expected that BN layers improve the netwrok's convergence rate and performance. By simulating the Segnet architecture with BN layers, I found that results are consistent with the reference paper: the network has reached a better optimum point with a higher rate. An interested person can find improvements of BN with convergence rate and the performance of the network by comparing the results of **Part A** and **Part B**. The codes and results of  **Part B** are provided in [Deep_Segnet_BN_Adam.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%202/PartB/Deep_Segnet_BN_Adam.ipynb) notebook.
