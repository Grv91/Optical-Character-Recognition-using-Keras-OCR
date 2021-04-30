# Optical-Character-Recognition-using-Keras-OCR
Machine learning projects

Problem Statement: 
  Identify text written on shipping containers.
  
Problem can be broken into 2 main parts:

1. Identification of container
Container identification is a classification problem. Since the volume of data was very small, I implemented data augmentation techniques like horizontal shift, vertical shift, brightness change and zoom in/zoom out to increase the vol 36 times.
Image classification model used is Xception as it is one of the most used pretrained model. There are other models as well and as a long term solution, we can compare scores of each of the models before finalization, but for this case, I limited my scope to this model only. I was able to achieve f1-score of .99 on test data. The Model was a little overfitted due to lack of negative data, but score was good on test data as well. However, we can use a better mix of data to better train the model (there were only 2 negative images). 
2. Identification of text on the container
For text identification, I used one of the most widely used OCR recognition packages in python - Keras-OCR
Even though package was able to identify most of the text correctly, there are few limitations, like it was not able to detect vertical text

Scope of improvement:
We can use pretrained models to identify the position of the container in the image so that only text inside the container is detected. However, It requires detailed labeling of the training data with the position of the container images.
Other OCR detection models can be created/used to identify vertical data as well.
Negative images are only 5% of total sample images. We can use minority oversampling techniques like SMOTE(synthetic minority oversampling technique) to increase samples of minority class
