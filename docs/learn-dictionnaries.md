# Learn dictionnaries

To learn a new dictionnary, you must:

* Turn the train option to `true`
* Specify a file name, with `.mat` extension
* Give the train dataset

**Exemple**
```matlab
hmax('your/train/dataset', 'Train', true, 'HLFiltersLocation', './data/my-custom-dictionnary.mat')
```