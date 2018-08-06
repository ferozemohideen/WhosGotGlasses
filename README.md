# Who's Got Glasses? :sunglasses:
This project is a webapp that explains the basis behind and practices K Nearest Neighbors classification, a technique I learned about in EGR 190: Introduction to Data Science, which I took in Spring 2018 at Duke University. Users have the ability to switch between 4 different images of people and view how well the classification algorithm did in assigning them to a group, with the option of changing the number of neighbors in classification.  
## Introduction to Django and Front-end Development
This also marked my first project written in Python using the Django framework. I learned a lot about views, inheritance, and the entire DNRY mentality that Django embodies, as well as styling methods using CSS and Bootstrap. Admittedly, I could have done a lot better on the latter front and hope to return to make the site more aesthetically pleasing once I have more experience.
## Statistical Learning
Pretty much all of the machine learning done in the project is located within the `testKNN.py` file - the rest is Django syntax and styling. The script works by first accessing a collection of 400 faces it converts into a suitable format and then uses as training data for the model. Sci-kit learn was used to fit a Nearest Neighbors model using this data, with the test faces held out. The classes of these four test cases were then predicted by the trained model and results are displayed, including a confusion matrix and ROC curve.

### TODO
- fix website styling (especially images)
- possibly introduce dimensionality reduction into analysis
- implement feature allowing users to upload their own images


Note: this repository was created because I realized that deployment to Heroku requires the git root to be the same as the Django project root. For a full list of commits, see my other repo, called `django-machine-learning`.


#### Side Note - KNN on images is almost never used
Here's why:
- Slow at test time: Although training time is pretty much O(1) (we are just copying references to the training data), the algorithm is <b>very</b> slow at test time -  we have to compare the distances of each test image to each image of the training set and sort that list. In contrast, we would much rather have an algorithm with long training times, which can be done somewhere else, and relatively short test times.
- Distance metrics on pixels are not very informative: The hyperparameter for a distance metric in our case was the L2 distance, but in the case of images, that's not especially useful for distinguishing pictures, in the sense that many drastically different test images can have the same L2 distance from a training image. We want something that better captures the variety in images.
- The curse of dimensionality: these images have <b>very</b> high dimensionality, and in order to justify using kNN, we ideally want a training set that covers the entire dimensional space (or rather, spans it). Although this is easy in lower dimensions, the curse of dimensionality requires us to have an exponential number of training images to satisfy this criteria, which we just do not have. Because the kNN algorithm doesn't really make any assumptions about any underlying manifolds in the separated data, the only way it can perform properly is if it has quite a dense sample of training points to work with. 400 images do not in any way cover a 10,304D space. 

HOWEVER, this exercise was still useful in better understanding the mechanics behind kNN, styling in HTML, web development with Django, and data analysis with Python and NumPy. But next time, I'll use a convolutional neural network...
