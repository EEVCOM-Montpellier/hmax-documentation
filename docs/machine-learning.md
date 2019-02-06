# Machine Learning

The code come with some tools to use machine learning models.  
Here, we will describe how to use them.

## Prepare your dataset

First, you must prepare your dataset.  
The simplest way is to have one folder per label containing your images.  
You encode you dataset and then split it for machine learning purposes.

1. Encode your images
```matlab
hmax('../dataset');
```
This will read recursively the `../dataset/` folder architecture and create a similar one in the `./result` folder.  
Each images will give a Matlab binary file containing the HMAX encoding.

2. If your folders are named corresponding to the label of the images, then you can run the following command:
```matlab
T = classifier.loadC2s('./results/');
```

Where `T` is a table containing HMAX encodings with corresponding labels.

3. Now you can use the data directly in a Machine Learning tool.  
The recommendation is to split the data (`T`) in two, one with *80%* of the observations for training and the other with the rest of the *20%* for validation.  

```matlab
[Ttrain Ttest] = classifier.splitdata(T, 0.8);
```

Then, you can use the Classification Learner toolbox to create a model.  
For our tests, we used a Linear SVM without PCA.

4. Finally, we can test our model
```matlab
averagePrecision = classifier.runtest(trainedModel, Ttest)
```

## Go further

Now that you know how to run HMAX, we will see how to run the code with GPU, parallel computing, with your own parameters, etc ...
