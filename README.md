# Computer-Vision-Merchandising-Resets

## Contents
* **Research Paper**: a paper that I wrote for my Computer Vision course. It goes in-depth about my research, methodology, and results. It was intended for submission into the FLAIRS Conference
* **iPython (Jupyter) Notebook**: a detailed python notebook that provides a basic template for my methods to be observed and executed

## Background
This was a simple research project that I created to fulfil a requirement for my Computer Vision class. The premise was to apply computer vision to whatever domain I desired. I chose the retail domain. Particularly, I was interested in how computer vision could be applied to merchandising resets, a process that take place in retail businesses to update inventory. While many different retail actions can constitute a 'reset' I chose the action that more closely aligned itself with the work that I did as a retail merchandiser. 
One such process was checking shelves for UPC tags and their respective products. Being able to ascertain the status of both of these objects allow the merchandiser to understand whether or not the product is (a) in-stock, (b) out-of-stock, (c) misplaced, or (d) discontinued. From a programming perspective, it seems perfectly feasible that such a task can be easily automated.

![image](https://user-images.githubusercontent.com/23637814/110267272-71207180-7f8d-11eb-831d-2cf707aff34f.png)


![image](https://user-images.githubusercontent.com/23637814/110266807-9bbdfa80-7f8c-11eb-88f1-9681ea88d698.png)


## Hypotheses
However, I chose to focus my efforts on illustrating the potentiality of computer vision with respects to the rudimentary processes of computer vision, namely barcode and image detection. After conducting research on different computer vision developments made in the retail domain, I decided that I would build upon an existing algorithm for barcode detection, and also to test how various hypotheses that I had about different aspects about the process. Specifically I chose Tunistra's Algorithm and decided to incorporate a noise-removal function in the process.

As for the aforementioned hypotheses, I had several:

1) Product-wise detection is inefficient in comparison to category-wise detection.
2) Noise-removal post-image-processing can increase accuracy of the model.
3) Noise-removal during training can increase the accuracy of the model.
4) The nature (size, shape, etc.) of the UPC tag affects accuracy of the model.

![image](https://user-images.githubusercontent.com/23637814/110266840-ac6e7080-7f8c-11eb-81e7-001574a95abb.png)


## Approach
To test these hypotheses, I came up the following plan. Note that these points correspond to those of the previous section.

1) Create two datasets of grocery products. One would be annotated according to product category while the other would be annotated according to individual product name. Then I would compare the two annotation processes, and train a seperate machine learning model for each dataset. Lastly, I would compare the accuracy of the models.
2) After training the model, I would apply a noise removal algorithm on the test set and then evaluate the model on the resulting set. I would compare results from the same evaluation test fro the previous point.
3) Before training the model, I would apply the noise removal algorithm on the test set. Then I would test the model, and evaluate its performance on a vanilla evaluation set, as well as the noise-removed set.
4) Create a seperate dataset, which would pertain to UPC tags rather than grocery products. This dataset would be images of retail shelves post-Tunistra's Algorithm. I would annotate the resulting images, targeting the UPC labels while making sure to annotate them according to the resulting contours (this would depend on the nature of the label). Then I would evaluate the model, gauging accuracy with respect to these labels.

To manage these goals I did the following:
* implemented Tunistra's algorithm for barcode detection ( https://www.researchgate.net/publication/249798154_Reading_Barcodes_from_Digital_Imagery )
* created and annotated four custom datasets ( https://www.kaggle.com/alitquanmallick/grocery-classifier )
* applied Tunistra's Algorithm to the applicable datasets
* implemented an image augmentation pipeline to diversify the datasets
* implemented a dataset-processing pipeline to streamline the machine learning process
* utilized YOLOv3 object detection model

![image](https://user-images.githubusercontent.com/23637814/110266700-5e596d00-7f8c-11eb-9b14-eb309a51fc0b.png)
![image](https://user-images.githubusercontent.com/23637814/110266748-792be180-7f8c-11eb-9a06-441fec4bac5a.png)
![image](https://user-images.githubusercontent.com/23637814/110267091-1b4bc980-7f8d-11eb-822f-f74ad30152f2.png)


