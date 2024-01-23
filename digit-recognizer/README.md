
Here are projects related to studying the commonly used MNIST data set, with the purpose of building models to accurately read digits from the set.

I started with the my-mnist-practice notebook, and then later rewrote it to submit to the related ongoing Kaggle competition.
I found that my initial model did not perform as well on the competition data as it appeared to on the testing data in my-mnist-practice notebook. 
I suspect that either the testing data in my notebook was not separate from the training set, or perhaps the data set sizes were significantly different 
between the data I used in my-mnist-practice.

One of the notebooks I used for the Kaggle competition is publicly available at [https://www.kaggle.com/code/michaeloliver137/digit-recognizer-2-targeted-resampling](https://www.kaggle.com/code/michaeloliver137/digit-recognizer-2-targeted-resampling), and will be added here in the future. In it, I developed a procedure to resample the training set based on weights from which classes the classifier underperformed on in the validaiton set.
