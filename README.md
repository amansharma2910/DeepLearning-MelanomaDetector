<h1 align = 'center'> Melanoma (Skin Cancer) Detection using Deep Learning</h1>

In this project, originally a Kaggle image classification competition, I worked on a deep learning pipeline that processes the input images of possible cancerous moles/tumors and predicts the probability of the mole(s) being melanoma (skin cancer). 

---

 Melanoma, also known as malignant melanoma, is a type of skin cancer that develops from the pigment-producing cells known as melanocytes. Melanomas typically occur in the skin but may rarely occur in the mouth, intestines or eyes. About 25% of melanomas develop from moles. Changes in a mole that can indicate melanoma include an increase in size, irregular edges, change in color, itchiness or skin breakdown.  
 
The primary cause of melanoma is ultraviolet light (UV) exposure in those with low levels of the skin pigment melanin. The UV light may be from the sun or other sources, such as tanning devices. Those with many moles, a history of affected family members and poor immune function are at greater risk. A number of rare genetic conditions such as xeroderma pigmentosum also increase the risk.

Diagnosis is by biopsy and analysis of any skin lesion that has signs of being potentially cancerous. 
— Source: [Wikipedia](https://en.wikipedia.org/wiki/Melanoma#:~:text=Melanoma%2C%20also%20known%20as%20malignant,or%20eye%20(uveal%20melanoma).)

Also check out [this page](https://www.skincancer.org/skin-cancer-information/melanoma/) on SkinCancer.org to know more about melanoma.

---
<h2>Project Objectives:</h2>

* Implementing a binary-classification deep learning CNN model in PyTorch capable of detecting presence of Melanoma from the images of the affected sites
* Performing basic EDA to find trends within the data
* Comparing the performance of different CNN architectures for the model

---

<h2>Understanding the Problem Statement:</h2>

The problem at hand is a binary-image-classification problem where given an input image, we want our model to classify the tumor/mole in the image as benign (non-cancerous) or malignant (cancerous).

Each image that we are dealing with is an 3-channelled RGB images of varying sizes. 

[Here](https://www.kaggle.com/c/siim-isic-melanoma-classification/data) is the link to the dataset.

---

<h2>Observations:</h2>

* There is a high sampling bias in the training data, with only around 1.76% of the data instances belonging to the 'malignant' class, and rest all belonging to the 'benign' class.

* The sampling bias affects the model's generalization on the inference data to a great extent. To tackle this problem, one can use different data augmentation techniques, or use external data to further train the model with more examples.

* In this dataset, the images can range upto 6000x5000px or even higher in size. Due to this, the dataset is very bad for I/O. Without preprocessing the images and applying transformations (resizing, augmentations etc.) while training, excruciatingly slowed down the training process to as low as 2hrs per epoch. On the other hand, applying all the transformations beforehand and preprocessing the image data beforehand reduced the time per epoch to as low as around 8 mins for the ResNet34 model, thus significantly improving the training speed. This shows the importance of data preprocessing and how it can affect our model's training.

Project currently ongoing. Will add more observations and conclusion as I progress.

