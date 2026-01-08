we got the data from tensorflow keras because it is much faster than  the scikitlearn fetch_openml 
here is the code for the dataset-
```
import tensorflow as tf
import matplotlib.pyplot as plt
(training, training_labels), (test, test_labels) = ts.keras.dataset.mnist.load_data()
plt.imshow(training[0].reshape(28,28), cmap = gray)
plt.axis("off")
```
 For Training we will use the *Stochastic Gradient Descent* (SDG). Good model for large data
```
from sklearn.linear_model import SGDClassifier
training_labels_5 = (training_labels == 5)
test_labels_5 = (test_labels == 5)
sdg_classify = SGDClassifier(random_state = 42)
# plt.imshow(training_images[0].reshape(28,28), cmap ='gray')
training_images_flat = training_images.reshape(60000,-1)
sdg_classify.fit(training_images_flat, training_labels_5)
```
Predicting-
```
sdg_classify.predict(training_images[0].reshape(1,784))
```

### [[Model Testing(Classification)]] 