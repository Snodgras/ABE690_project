#README

#Data 
* Initial practice data came from PalDal `https://www.paldat.org/`
	* Gathered images from Poales group with light microscopy
	* labeled as `number_genus_species.jpg`

This code was influenced by _Marcos et al 2015_, opencv tutorials, the learn opencv blog, 
and the pyimagesearch blog.

#Image processing and measurements
Use the `Snodgrass_Pollen_Identifier.ipynb` file to run this code and see how it works.

In summary, images are read in using `opencv2` and converted to grayscale.
Histograms of the grayscale helped picke the right pixel value range for thresholding.
Blurring, binary thresholding, masking, and floodfilling simplify the image so that the 
background is black and the grain, size bar are white. 
The size bar is cropped out to count the number of white pixels within the grain. 
This can be done because the size bar is in the same pixel position for each image.
The cropped size bar image is used to convert the number of pixels to micrometers (um). 
This is then used to calculate the area of white pixels in the image into um^2. 
Results are then added to a numpy array.
After all images have been processed, the results and the file names are put together into a pandas dataframe.

#Models
The resulting data from the image processing could be fed into a support vector machine (SVM) algorithm to classify images to 2 different categories.

#Future work
1. Verify that the areas measured by the python code are accurate (ground truth)
2. Test an SVM model to differentiate between different classes of pollen
	i. use the code from meeting 8


#References

Marcos et al. 2015. "Automated pollen identification using microscopic imaging and texture analysis". 
_Micron_ 68:36-46.

opencv tutorials:
	`https://docs.opencv.org/master/d7/d4d/tutorial_py_thresholding.html`
	`https://docs.opencv.org/trunk/d3/d05/tutorial_py_table_of_contents_contours.html`
	``
The learn opencv blog:
	`https://www.learnopencv.com/filling-holes-in-an-image-using-opencv-python-c/`
	`https://www.learnopencv.com/filling-holes-in-an-image-using-opencv-python-c/`

The Pyimagesearch blog:
	`https://www.pyimagesearch.com/tag/pixels-per-metric/`
	`https://www.pyimagesearch.com/2016/03/28/measuring-size-of-objects-in-an-image-with-opencv/`


