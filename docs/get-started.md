# Get started

This section will show you how run the code for a classification.

## Prepare your dataset

First of all, you must prepare your dataset.  
HMAX require a training step, so you must have a training and a testing dataset.

We recommand to have at least 15 images per class to train the model.

In your test dataset, you must have one folder per class, with your images in it.

## Quick start

This will show you how to run HMAX with the default configuration. Computations are not parallized or putted on the GPU.  
You should do this on a small dataset first as it can take some time.

1 . Open the project with Matlab.

2 . Then, you need to train the model with the dataset you have prepared
```matlab
hmax('../dataset/train/', 'Train', true);
```

3 . Run it on your test dataset
```matlab
hmax('../dataset/test/');
```

This will read recursively the `../dataset/test/` folder architecture and create a similar one in the `./result` folder.  
Each images will give a Matlab binary file containing the HMAX encoding.

4 . If your folders are named corresponding to the class name of the images, then you can run the following command:
```matlab
T = classifier.loadC2s('./results/');
```

Where `T` is a table containing HMAX encodings with corresponding labels.

## Machine Learning

Once you've done the step `4.`, you can use the data in a Machine Learning tool.  
The recommandation is to split the data (`T`) in two, one with *80%* of the observations for training and the other with the rest of the *20%* for validation.  

```matlab
[Ttrain Ttest] = classifier.splitdata(T, 0.8);
```

Then, you can use the Classification Learner toolbox to create a model.  
For our tests, we used a Linear SVM without PCA.

Finally, we can test our model
```matlab
averagePrecision = classifier.runtest(trainedModel, Ttest)
```

## Go further

Now that you know how to run HMAX, we will see how to run the code with GPU, parallel computing, with your own parameters, etc ...