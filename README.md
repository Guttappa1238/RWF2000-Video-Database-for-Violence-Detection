## RWF2000 - A Large Scale Video Database for Violence Detection



### Introduction

With the increasing of surveillance cameras in modern cities, huge amount of videos can be collected. While there are insufficient human resource for  monitoring all the screens at  one time. 

We are considering how to use techniques of video understanding to detect violent behavior so that it can give a quick alarm in time.



### File Description

- **Preprocess** contains the python script to transform original video dataset to .npy files. Each .npy file is a tensor with shape = [nb_frames, img_height, img_width, 5]. The last channel contains 3 layers for RGB components and 2 layers for optical flows (vertical and horizontal components, respectively ).

- **Networks** contain the keras implemention of our propsoed model. Also, the training scripts of single stream are provided here.

- **Models** contains the pre-trained model implemented by Keras.

  

### Dataset

- Collected raw surveillance videos from YouTube, sliced them into clips within 5s at 30 fps, and labeled each clip as Violent or Non-Violent Behavior。

- Dropped duplicated contents which appear in both training set and validation set.

- Finally we got 2000 clips and 300,000 frames as a new data set for real-world violent behavior detection under surveillance camera.

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/demo1.gif" width="400px" height="250px">
  
  

### Problems

Since all the videos are captured by surveillance cameras in public places, many of them may not have a good imaging quality due to dark environment, fast movement of object, lighting blur, etc. Here are some examples:

- Only part of the person appears in the picture

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/blocked.gif" width="400px" height="250px">

  

- Crowds and chaos

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/crowded.gif" width="400px" height="250px">

- Small object at far distance

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/far_distance.gif" width="400px" height="250px">

- Low resolution

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/low_resolution.gif" width="400px" height="250px">

- Transient action

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/transient.gif" width="400px" height="250px">



### Demo

- Example - 1

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/result_2.gif" width="800px" height="400px">



- Example - 2

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/result_1.gif" width="800px" height="400px">

   

### Download

To download the released dataset, please:

1. download the *Agreement Sheet.pdf* (attached in this Repo) and sign it. 
2. Send the PDF version of scanned *Agreement Sheet* with signature to ming.cheng@dukekunshan.edu.cn
3. We will send an e-mail with download link to you as soon as possible.

 

Kindly remind: using the proposed dataset, please cite:

```
@inproceedings{cheng2021rwf,
  title={Rwf-2000: An open large scale video database for violence detection},
  author={Cheng, Ming and Cai, Kunjing and Li, Ming},
  booktitle={2020 25th International Conference on Pattern Recognition (ICPR)},
  pages={4183--4190},
  year={2021},
  organization={IEEE}
}
```

### Note

- Since the dataset contains 2,000 video clips extracted from about 1,000 unique videos, we have manually checked the train set and test set to avoid the data leakage between different parts. We suggest you to keep the original partition and only separate a validation set from the train set, but do not re-shuffle the entire dataset.
- The data is compressed into separate blocks. You need to decompress it by following ways:
  - Windows PC:  put all the files under the same folder, and then de-compress the first on e. All the data will be de-compressed automatically. (7Zip.exe is recommended for the compression tool)
  - Linux: concatenate the separate file blocks together, and then use unzip to decompress it.  















