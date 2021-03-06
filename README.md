# Ranking-Comedians-Face



*Abstract*— This is a proposal for a deep learning project that ranks comedians' looks. First, create a CNN model that evaluates the appearance rank using the FBP5000 dataset. Then, the appearance rank is measured using the comedian image as a test set. Keywords—SCUT-FBP, Classification, Image, Ranking, CNN

# I.  Introduction

 I wanted to work on an image related project. Among them, I chose 'face', which comes to mind when it comes to images. The word 'face' is naturally reminiscent of appearance ranking. I thought it would be great if the deep learning model would rank people's appearance. Therefore, I would like to create a model that gives scores to people's looks with train data, and conduct tests and evaluations with images of Korean comedians on that model. The model was referenced in the study introduced in the second chapter. I will add additional layers to the model created in the study or modify the parameters to make the val_loss lower.

# II.  Related Work 

 Beauty Score[1]— I found a study to classify the faces of k-pop BTS. In this study, the SCUT-FBP5500 Dataset was used and the model was created using the CNN model. Since then, it ranks the faces of BTS using BTS images. The model with the lowest loss in the study was 0.3863. Appearance rankings were measured in order: Jungkook – V – Jin &RM (same rank) – JHope – Jimin – Suga

# III.  Data Description

### A.  Train set

 The SCUT-FBP5500 Dataset can be divided into four subsets with different races and gender, including 2000 Asian females(AF), 2000 Asian males(AM), 750 Caucasian females(CF) and 750 Caucasian males(CM). Most of the images of the SCUT-FBP5500 were collected from Internet, where some portions of Asian faces were from the DataTang, GuangZhouXiangSu and our laboratory, and some Caucasian faces were from the 10k US Adult Faces database. All the images are labeled with beauty scores ranging from [1, 5] by totally 60 volunteers, and 86 facial landmarks are also located to the significant facial components of each images.

 

<img width="235" alt="Picture1" src="https://user-images.githubusercontent.com/33794732/86546095-f15d8580-bf6d-11ea-8627-6790101f821c.png">

Fig. 1. The images with different facial properties and beauty scores from the proposed SCUT-FBP5500 benchmark dataset. [2]

 

### B.  Test set

The test set data uses 7 comedian images as follows. This image was taken from a program called Korea's Infinite Challenge. At the time, the program was held under the theme of 'You are handsome'.

<img width="242" alt="Picture2" src="https://user-images.githubusercontent.com/33794732/86546098-f4587600-bf6d-11ea-8c3b-45a8c5b1af70.png">

Fig. 2. The images of Infinite Challenge Members 

 

# IV. Experiments: Instance Segmentation

### A.  How to collect data

 Train data can download from the site [3]. It is the data set provided by the SCUT-FBP5500 paper. Test data can download from the broadcasting station website [4].

### B.  Method of performance comparison

 I will compare the performance of the model with the val_loss value.

 

# V.  Expected Conclusion

In this study, I will add a layer or apply another activation function. In this way, various hyperparameter values will be changed. I would expect to make val_loss lower and make a better model. However, the data used to train the model were evaluated by 60 Chinese volunteers. Therefore, the results applied to the model are subjective.

# VI.  Cases

I created a CNN model that ranks faces using the SCUT-FBP5500 Dataset. In the process, 90% of the SCUT-FBP5500 Dataset was used as a test set and the remaining 10% as a validation set. Afterwards, techniques such as layer addition, imageDataGenerator, and dropout were used to find a model that minimizes val_loss and improved performance. A total of 8 cases were compared and analyzed.

| <img width="542" alt="Screen Shot 2020-06-23 at 4 19 37 PM" src="https://user-images.githubusercontent.com/33794732/85373776-b96a4180-b56e-11ea-9758-1da0ecf22c7f.png"> | <img width="544" alt="Screen Shot 2020-06-23 at 4 20 14 PM" src="https://user-images.githubusercontent.com/33794732/85373789-be2ef580-b56e-11ea-85f3-cac00654fb01.png"> | <img width="541" alt="Screen Shot 2020-06-23 at 4 20 23 PM" src="https://user-images.githubusercontent.com/33794732/85373792-bec78c00-b56e-11ea-8ee4-6ee069bdfc99.png"> | <img width="541" alt="Screen Shot 2020-06-23 at 4 20 32 PM" src="https://user-images.githubusercontent.com/33794732/85373793-bf602280-b56e-11ea-9108-74ed6f8cb4cf.png"> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img width="542" alt="Screen Shot 2020-06-23 at 4 20 50 PM" src="https://user-images.githubusercontent.com/33794732/85373796-bff8b900-b56e-11ea-8829-0df9a0052c37.png"> | <img width="542" alt="Screen Shot 2020-06-23 at 4 20 59 PM" src="https://user-images.githubusercontent.com/33794732/85373799-c0914f80-b56e-11ea-8f83-40a55286c94d.png"> | <img width="542" alt="Screen Shot 2020-06-23 at 4 21 09 PM" src="https://user-images.githubusercontent.com/33794732/85373800-c129e600-b56e-11ea-9b2a-0225fae36c51.png"> | <img width="542" alt="Screen Shot 2020-06-23 at 4 21 22 PM" src="https://user-images.githubusercontent.com/33794732/85373801-c1c27c80-b56e-11ea-8a74-94125fe78e95.png"> |


# VII. Results

<img width="773" alt="Screen Shot 2020-06-23 at 4 35 09 PM" src="https://user-images.githubusercontent.com/33794732/85374315-8aa09b00-b56f-11ea-8e84-690f70262230.png">

This is the result of the final voting in the actual Infinite Challenge program. This is the final result of reflecting the results of on-site voting, online, specialist, and overseas voting at the same rate (25% each). Among them, I would like to compare the results applied to the model of Case 8, which had a low val_loss. It is similar that Hong Chul is at the top and Myeong-Soo has the lowest score, but it is difficult to find a common point in the rest. It's no wonder that the results are different. This is because the data used to train the model itself is subjective. I thought that this study could be further developed and used in various marketing strategies even if it is not necessarily the face of comedians. It would be useful to conduct experiments such as'Favorite Face in the United States','Favorite Face in China', and'Favorite Face in Korea' and use it as a cultural content business targeting the culture.



##### References

[1]   https://github.com/WonJunPark/beauty_score

[2]   LIANG, Lingyu, et al. Scut-fbp5500: A diverse benchmark dataset for multi-paradigm facial beauty prediction. In: *2018 24th International Conference on Pattern Recognition (ICPR)*. IEEE, 2018. 

[3]   https://drive.google.com/file/d/1un5CjTz_49Lg6MTNQn99WD7FjFqEJGoY/view 

[4]   http://www.imbc.com/broad/tv/ent/challenge/event/minam/index.html

 



 

 

 

 
