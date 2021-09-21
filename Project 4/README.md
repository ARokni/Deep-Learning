# Fourth Project
* In this project, I have implemented an **`Image-Captioning`** task utilizing **`CNN`** and **`LSTM`**  on **`Flickr8k`** dataset.

* **Dataset**: Flickr8k consists of two different part: **Images** and **Captions**. The dataset contains 8092 images of different sizes, and there are five captions for each image. 
    
* **Preprocess**: 
    * **Images**
        - First, due to the varied sizes of images, I have utilized a transformation to resize all images to a specified shape.
        - Second, I applied a random crop on each image for the **`Data Augmentation`** issue.
        - In the end, I normalized all the images in order to cope with the problems of uneven  features' scales.
    * **Captions**
        -   First, I loaded the captions into a data frame, then I  lowered cased all the letters and eliminated all punctuations and irrelevant characters from the captions.
        - Second, I constructed  a **`Vocabulary`** based on the captions.
        - In the end, I have utilized **`Padding`** to have sentences with the same length at each batch of the data. 
    
* **Network's Model** 
    - I have applied a **Hybrid** LSTM and CNN architecture: the CNN part extracts the features of a given image, then the LSTM part utilizes the features in order to provide a meaningful sentence describes the image. 
    -  For the CNN part, I have applied a pre-trained **`Resnet18`**. The last layer of the Resnet is replaced with a linear layer in order to provide the required features of an image.
    - For the LSTM part, I utilized the LSTM module that is available in PyTorch. The output of the LSTM is given to a linear layer that converts the output of the LSTM to a vector with the **vocabulary** size dimension.
    - After the model was trained,  I implemented a function to caption the test images. This function is provided in my notebook with **caption_prediction**.

    ![alt text](https://github.com/ARokni/Deep-Learning/blob/main/Project%204/img/model.JPG)
    
* In **Part 1**, all layers of  **Resnet18** except the last linear layer have been frozen in the training process. **`Cross Entropy`** and **`Adam`** are utilized as a loss function and an optimizer. The hyperparameters have been determined by means of search and trail. The codes and results are provided in [Deep_ImageCaptioning_part1.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%204/Part1/Deep_ImageCaptioning_part1.ipynb).

* In **Part 2**, in contrast to **Part 1**, all layers of **Resnet18** trained with the rest of the model. All other conditions are the same as **Part 1**. The codes and results are provided in [Deep_ImageCaptioning_part2.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%204/Part2/Deep_ImageCaptioning_part2.ipynb).
