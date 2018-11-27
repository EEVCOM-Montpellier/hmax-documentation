# In deep

In this section, we will show how to use advanced parameters in HMAX.  
If you haven't read it yet, you should start with the [Get started](/get-started) section.

## How to specify parameters

There is two ways to set parameters in the program:

1. Directly through the Matlab command
2. From a configuration file

The priority is given to:
1. Parameters set through the Matlab command
2. Parameters written in the configuration file
3. Parameters set internally

That's why in the [Get started](/get-started) section, we wrote:
```matlab
hmax('../dataset/train/', 'Train', true);
```
The `Train` parameter is set to `false` internally and in the default configuration file.  
Setting the parameter to `true` will override the default value.

## Avalaible parameters

| Name                      | Description                         | Type expected      | Default value                |
|---------------------------|-------------------------------------|--------------------|------------------------------|
| ConfigurationFile         | Custom configuration file           | String - JSON file | `"./defaultParameters.json"` |
| Output                    | Custom output directory             | String - Directory | `"./results"`                |
| GPU                       | Use GPU for computation             | Boolean            | `false`                      |
| Parallel                  | Use parallel computing              | Boolean            | `false`                      |
| Engine                    | Specify an algorithm to use         | String             | `"sparseCodingColor"`              |
| ImageSize                 | Resize image to this size in pixels | Integer            | `140`                        |
| GaborNbOrientations       | Nb. of oritentions for Gabor filters| Integer            | `4`                          |
| GaborAspectRatio          | Aspect ratio of Gabor filters       | Float              | `0.3`                        |
| GaborEffectiveWidth       | Width of Gabor filters              | Float[]            | `[2.8, 3.6, 4.5, ..., 18.2]` |
| GaborWavelength           | Wavelength of Gabor filters         | Float[]            | `[3.5, 4.6, 5.6, ..., 22.8]` |
| GaborSizes                | Sizes of Gabor filters              | Integer[]          | `[7, 9, 11, 13, ..., 39]`    |
| FiltersSizes              | Sizes of S2 filters                 | Integer[]          | `[4, 8, 12, 16]`             |
| MaxPoolingSizes           | Size of the max pooling             | Integer[]          | `[8, 8, 10, 10, ..., 22]`    |
| ColorNbChannels           | Nb. of color channels               | Integer            | `4`                          |
| SparseCodingFilterSize    | Sizes of S2 filters (sparse HMAX)   | Integer            | `12`                         |
| SparseCodingNbPatches     | Nb. of patches extracted (sparse HMAX)| Integer            | `10000`                      |
| SparseCodingBatchSize     |                                     | Integer            | `1000`                       |
| SparseCodingNbIterations  |                                     | Integer            | `2`                          |
| SparseCodingPenalty       |                                     | Float              | `0.2`                        |
| NbFilters                 |                                     | Integer            | `1000`                       |
| Train                     | Train the model                     | Boolean            | `false`                      |


### Engine 
Choose between: **classic**, **sparseCoding**, **color** or **sparseColor**

### ImageSize
The program will alway resize input images, so the size will be uniform. Bigger they are, slower the execution will be.

### GaborEffectiveWidth
Default values: `[2.8, 3.6, 4.5, 5.4, 6.3, 7.3, 8.2, 9.2, 10.2, 11.3, 12.3, 13.4, 14.6, 15.8, 17.0, 18.2]`

### GaborWavelength
Default values: `[3.5, 4.6, 5.6, 6.8, 7.9, 9.1, 10.3, 11.5, 12.7, 14.1, 15.4, 16.8, 18.2, 19.7, 21.2, 22.8]`

### GaborFilterSizes
Default values: `[7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37]`

### MaxPoolingSizes
Default values: `[8, 8, 10, 10, 12, 12, 14, 14, 16, 16, 18, 18, 20, 20, 22, 22]` 
