# Second Project
* In this project I have implemented a `Segnet Network` in order to perform the `Semantic-Segmentation` task on `UTKFace` dataset.
    
* In **Part A** a **segnet** architecture [[1]](#1) has been implemented; however, the training scheme and hyperparameters are not the same as the reference papaer: In contrast to [[1]](#1) , I have trained the whole network at once (instead of training different encoder-decoder pairs in seperate steps). Moreover I have utilized two optimizers, `SGD` and `Adam`, to train the net and to compare the results. Consistent with the grounds mentioned in [[2]](#2) , a smart person can figure out from the results of my notebooks that **Adam** has a higher convergance rate than **SGD** optimzer, which results in a better performance in lower iterations. The codes and results are provided in [Deep_Segnet_Adam.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%202/PartA/Deep_Segnet_Adam.ipynb) (**Segnet** with **Adam optimizer**) and in [Deep_Segnet_SGD.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%202/PartA/Deep_Segnet_SGD.ipynb) (Segnet with **SGD** optimizer) notebooks.

* In **Part B** the architecture of **Part A** has been enriched with `Batch-Normalization (BN)` layers. On the groud of [[3]](#3), I expected that BN layers improve the convergance rate and the performance of the network. By simulating the Segnet architecture with BN layers, I found that results are consistent with the reference paper: the network has reached better optimum point with a higher rate. An interested person can find improvements of BN with convergence rate and the performance of the network by comparing the results of the **Part A** and the **Part B**. The codes and results of the **Part B** are provided in [Deep_Segnet_BN_Adam.ipynb](https://github.com/ARokni/Deep-Learning/blob/main/Project%202/PartB/Deep_Segnet_BN_Adam.ipynb) notebook.

## References
<a id="1">[1]</a> 
[Badrinarayanan, V., Handa, A. and Cipolla, R., 2015. Segnet: A deep convolutional encoder-decoder architecture for robust semantic pixel-wise labelling. arXiv preprint arXiv:1505.07293.](https://arxiv.org/abs/1505.07293)

<a id="2">[2]</a> 
[Zhang, J., Karimireddy, S.P., Veit, A., Kim, S., Reddi, S.J., Kumar, S. and Sra, S., 2019. Why are adaptive methods good for attention models?. arXiv preprint arXiv:1912.03194.](https://arxiv.org/abs/1912.03194)

<a id="3">[3]</a> 
[Ioffe, S. and Szegedy, C., 2015, June. Batch normalization: Accelerating deep network training by reducing internal covariate shift. In International conference on machine learning (pp. 448-456). PMLR.](http://proceedings.mlr.press/v37/ioffe15.html)