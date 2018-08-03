# Who's Got Glasses?
This project is a webapp that explains the basis behind and practices K Nearest Neighbors classification, a technique I learned about in EGR 190: Introduction to Data Science, which I took in Spring 2018 at Duke University. Users have the ability to switch between 4 different images of people and view how well the classification algorithm did in assigning them to a group, with the option of changing the number of neighbors in classification.  
## Introduction to Django and Front-end Development
This also marked my first project written in Python using the Django framework. I learned a lot about views, inheritance, and the entire DNRY mentality that Django embodies, as well as styling methods using CSS and Bootstrap. Admittedly, I could have done a lot better on the latter front and hope to return to make the site more aesthetically pleasing once I have more experience.
## Statistical Learning
Pretty much all of the machine learning done in the project is located within the `testKNN.py` file - the rest is Django syntax and styling. The script works by first accessing a collection of 400 faces it converts into a suitable format and then uses as training data for the model. Sci-kit learn was used to fit a Nearest Neighbors model using this data, with the test faces held out. The classes of these four test cases were then predicted by the trained model and results are displayed, including a confusion matrix and ROC curve.
### TO DO
- fix website styling (especially images)
- possibly introduce dimensionality reduction into analysis
- implement feature allowing users to upload their own images
