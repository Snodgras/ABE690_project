#README

#Data 
* Initial practice data came from PalDal `https://www.paldat.org/`
	* Gathered images from Poales group with light microscopy and spheroidal grains
	* labeled a `number_genus_species.jpg`

#Segmentation of pollen grain from background
_Marcos et al 2015_ did the following pre-processing
1. Binarization using Otsu-based method
2. Found the region with the maximum area
3. Filled any holes withint he selected region
4. The borders were defined using erosion and dilation operators
5. Filled any remaining holes
6. Trimmed both image and its binary mask
7. removed the background (multiply the corresponding mask to set background pixels to 0)
*Further processing for texture analysis*

Plantcv VIS tutorial

#Models
Look at Meeting 8 notes

# Harris corner detection code comes from: https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_feature2d/py_features_harris/py_features_harris.html

# this code comes from https://www.pyimagesearch.com/2016/03/28/measuring-size-of-objects-in-an-image-with-opencv/
```source activate ABE690```
```python find_size.py --image 1_Alopecurus_pratensis.jpg --width 10```
