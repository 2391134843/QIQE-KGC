# QIQE-KGC
*source code and data for "Knowledge Graph Completion Method Based on Quantum Embedding and Quaternion Interaction Enhancement"*

Because github limits the size of uploaded files, we put the code and data in the google cloud disk.[https://drive.google.com/file/d/1tueH04ZIBCzSuWiKTBMl5UAPuU3JRzFk/view?usp=sharing]
A more detailed introduction is provided after the dissertation is accepted.


Our model is based on [OpenKE](https://github.com/thunlp/OpenKE) and [E2R](https://github.com/IBM/e2r).
## Requirements
* python>=3.7
* torch>=1.8 
* tqdm

All experiments are run with 2 RTX 3090(24GB) GPUs.

## How to Run
Each data set we have equipped with independent files and hyperparameters
#### 1.If only to reproduce our results
Download the model from Google cloud disk and unzip it.
Take the reproduction of FB15K dataset as an example.Go to the model file first.
```
cd QIQE-KGC
cd fb15k
```
Run the underlying C++ file of OpenKE, and run Test.py directly to reproduce the results.
```
bash bash make.sh
python Test.py
```
#### 2.Train the model yourself
Training a model can be time consuming.
Download the model from Google cloud disk and unzip it.
Take the reproduction of FB15K dataset as an example.Go to the model file first.
```
cd QIQE-KGC
cd fb15k
```
Run the underlying C++ file of OpenKE, and run Test.py directly to reproduce the results.
```
bash make.sh
python Train.py
python Test.py
```



## Troubleshooting

##### 1.OSError: /data/KE/OpenKE/release/Base.so: invalid ELF header.

*Please don't forget to run the underlying C++ file of OpenKE first.*

##### 2.RuntimeError: Attempting to deserialize object on CUDA device 1 but torch.cuda.device_count() is 1. Please use torch.load with map_location to map your storages to an existing device.
*If you only have one GPU, modify the cuda number.*
