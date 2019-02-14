# Learn dictionnaries

To learn a new dictionnary, you must:

* Turn the train option to `true`
* Specify a file name, with `.mat` extension, where to save the dictionnary
* Give the train dataset

**Exemple**
```matlab
hmax('your/train/dataset', 'Train', true, 'HLFiltersLocation', './data/my-custom-dictionnary.mat')
```

You must use the same `Engine` in the training and the execution session.  
I.e., if you learn a `sparseCoding` dictionnary, you must execute a `sparseCoding` encoding, you can't use this dictionnary with `classic`, `color` or even `sparseColor`.