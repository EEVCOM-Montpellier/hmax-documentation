# Performance test with Caltech101

We compared our version of HMAX (Renoult et al. 2019) to that provided by Thomas Serre's Lab, available here:
[https://github.com/serre-lab/color_hmax](https://github.com/serre-lab/color_hmax)

Comparisons were made on a classification task using the Caltech101 dataset, available [here](http://www.vision.caltech.edu/Image_Datasets/Caltech101/).
This dataset contains 102 categories, which include between 31 and more than 800 images.

Analyses were performed with the 102 categories, and with a reduced database of only 20 categories. 
The Caltech20 dataset contained the following categories:

|            |                 |             |               |
|------------|-----------------|-------------|---------------|
| Airplanes  | Electric guitar | Hedgehog    | Minaret       |
| Binocular  | Emu             | Joshua tree | Pigeon        |
| Chandelier | Faces           | Laptop      | Rooster       |
| Dolphin    | Gerenuk         | Mandolin    | Sea horse     |
| Strawberry | Trilobite       | Water lilly | Windsor chair |

Images were resized to 140 pix for the smallest side, keeping the aspect ratio unchanged. We used 15 images per category to first learn the set of S2 filters, extracting 1,000 filters from C1 with HMAX and 4,000 filters with colour HMAX (1,000 for each DO channel), and learning 250 filters with sparse-HMAX (both greyscale and colour versions). We used a red-cyan opponent channel in addition to the yellow-blue, red-green and achromatic channels (Zhang et al., 2012). For the classification task, we randomly selected 31 pictures from each of the 102 categories and encoded them with the previously learned HMAX models. Among these 31 pictures, 25 were used for training the classifier and six for testing. The multiclass classifier consisted of 102 binary linear Support Vector Machines (one per category). During training, we applied a cross-validation procedure with five clusters to limit over-fitting.

## Results - Caltech 20

|                        | Renoult et al. | Serre et al. | Renoult et al. | Serre et al. | Renoult et al. | Renoult et al.     |
|------------------------|----------------|--------------|----------------|--------------|----------------|--------------------|
| Engine                 | Classic        | Gray         | Color          | Color DO     | Sparse coding  | Sparse coding color|
| Correct classification | 57.14%         | 58.57%       | 64.29%         | 50.71%       | 45.71%         | 53.57%             |
| Execution time         | 57m25s         | 1h16m16s     | 13h28m22s      | 11h09m34s    | 2h48m00s       | 9h23m42s           |

## Results - Caltech 101

|                        | Renoult et al. | Serre et al. | Renoult et al. | Serre et al. | Renoult et al. | Renoult et al.     |
|------------------------|----------------|--------------|----------------|--------------|----------------|--------------------|
| Engine                 | Classic        | Gray         | Color          | Color DO     | Sparse coding  | Sparse coding color|
| Correct classification | 31.79%         | 27.45%       | 29.55%         | 25.63%       | 18.77%         | 23.11%             |
| Execution time         | 4h38m33s       | 6h4m8s       | 2d21h22m2s     | 2d4h11m30s   | 4h52m30        | 20h53m43           |
