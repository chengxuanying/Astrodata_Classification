# Biendata BAAI Astrodata 2019
This is our solution for [BAAI Astrodata 2019](https://www.biendata.com/competition/astrodata2019/)。 We implemented a simple but powerful deep conv model and ranked 2rd in the test set.

### Feature
* Codes are neat and clear using skorch. 
* Using a 6-block-layer Resnet 
* Using Squeeze layer for fast convergence
* Using CEloss for training, L1loss for fintuning
* Scores are stable when training

### Exploratory Data Analysis
You can refer to this slides [here](https://drive.google.com/open?id=113bZYDeGGayw9WWeeoZLTH3rxYEog7blXq6GyXx_ipY) or the bilibili video [here](https://www.bilibili.com/video/BV12E411W7b2). The bilibili video quickly goes through the task background and the data distribution. And it also provides a easy-to-start baseline using LightGBM and hand-crafted features.

### Our pipeline
1. Open the jupyter notebook ```jupyter lab or jupyter notebook```
2. **Cleaning the Dataset** ```Run 01*.ipynb```. In this notebook, we cleaned the dataset and convert the data type into float32 to save memory usage. Also, we used the binary npy files as the storage format.
2. **Training** ```Run 03*.ipynb```, In our experiment, we trained 16 models using 4 gpus sharing the same model and hyperparameter. That is, we repeatly run the same code for 16 times to reduce the varience and boost the performance of our models.
3. **Inference** ```Run04*.ipynb```, We simply infered the result using 1 GPU and average the output from 16 models as our final result. And this leads to our final result with Macro-F1 0.98627835085156.

### Members of Team Dlutycx
Haha, it is a solo team:
**Chengxuan Ying**, Dalian University of Technology (应承轩 大连理工大学)
