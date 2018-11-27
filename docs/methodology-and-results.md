# Performance test with Caltech101

We compared our version of HMAX (Renoult et al. 2019) to that provided by Thomas Serre's Lab, available here:


of efficiency and its different extensions available in literature are compare through the Caltech101 dataset, which you can find [here](http://www.vision.caltech.edu/Image_Datasets/Caltech101/).
This dataset contains 102 categories, each one including between 31 and more than 800 images.

As we want a multi-class classifier, we need a balanced dataset. That's why we only take the first 31 images for all the categories.

For the HMAX training, we take the first 15 images of each categories, due to Serre et al. implementation. This is an issue because half of our testing images are present in the training stage.  
That's why in a second time, we created an alternative dataset in witch training images were taken randomly in the complete dataset.

HMAX is demanding in resources and in time and in order to quickly test the algorithm in a reasonable amount of time, so we created a subset dataset that we called Caltech 20. It contains theses categories:

|            |                 |             |               |
|------------|-----------------|-------------|---------------|
| Airplanes  | Electric guitar | Hedgehog    | Minaret       |
| Binocular  | Emu             | Joshua tree | Pigeon        |
| Chandelier | Faces           | Laptop      | Rooster       |
| Dolphin    | Gerenuk         | Mandolin    | Sea horse     |
| Strawberry | Trilobite       | Water lilly | Windsor chair |

## Comparison with Serre et al. algorithm - Caltech 20

|                             | Renoult et al. | Serre et al. | Renoult et al. | Serre et al. | Renoult et al. |
|-----------------------------|----------------|--------------|----------------|--------------|----------------|
| Engine                      | Classic        | Gray         | Color          | Color DO     | Sparse coding  |
| Correct classification rate | 57.14%         | 58.57%       | 64.29%         | 50.71%       | 45.71%         |
| Execution time              | 57m25s         | 1h16m16s     | 13h28m22s      | 11h09m34s    | 2h48m00s        |

## Comparison with Serre et al. algorithm - Caltech 101

|                             | Renoult et al. | Serre et al. | Renoult et al. | Serre et al. | Renoult et al. |
|-----------------------------|----------------|--------------|----------------|--------------|----------------|
| Engine                      | Classic        | Gray         | Color          | Color DO     | Sparse coding  |
| Correct classification rate | 31.79%         | 27.45%       | 29.55%         | 25.63%       | --.--%         |
| Execution time              | 4h38m33s       | 6h4m8s       | 2d21h22m2s     | 2d4h11m30s   | -h--m--s       |
