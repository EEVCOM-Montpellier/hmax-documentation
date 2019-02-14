# Get started

This section will show you how to process images with the HMAX algorithm.

## Quick start

HMAX needs a dictionnary of high level filters (later HLFilters) in order to work.  
Renoult and al. HMAX come with pre-build dictionnaries, so that you will easely process your images.

Theses steps bellow run Renoult HMAX with the default configuration and dictionnany:

1. Open the project with Matlab.

2. Run the code on your images
```matlab
hmax('path/to/your/images');
```

This will read recursively the `path/to/your/images` folder architecture and create a similar one in the `./result` folder.  
Each images will give a Matlab binary file containing the HMAX encoding.

## Troubleshouting 

**The code doesn't run because I don't have the Parallelization package**  
You can still run it by specifiyng that you don't want to use parallelization:
```matlab
hmax('path/to/your/images', 'Parallel', false);
```

## What's next?

* Learn a custom HLFilter dictonnary: [Learn dictionnaries](/learn-dictionnaries.md)
* Learn how to use custom parameters: [Custom parameters](/custom-parameters.md)
* Use Machine Learning tools: [Machine Learning](/machine-learning.md)
