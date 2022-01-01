# Detection-of-DR-using-LBP

## Proposed System
![Screenshot 2022-01-01 192222](https://user-images.githubusercontent.com/93415381/147852137-8780683b-4b66-40cc-8fab-54acf6703604.png)

### Preprocessing
We use images from different sources, the size of image varies. Hence we need to rescale the images using length of horizontal diameter of fundus as reference. Here Bicubic 
interpolation is used for resizing of image. The output pixel is weighted average of pixels in nearest 4*4 neighbourhood. After rescaling, to remove noise we use Median filter 
using 3*3 neighbourhood.
![Screenshot 2022-01-01 192607](https://user-images.githubusercontent.com/93415381/147852180-cc76e742-a438-47fa-802b-85588489c47b.png)

### FEATURE EXTRACTION
The feature extraction consists of different stages. First we use Water shed algorithm to separate foreground and background of the image. Watershed algorithm which is a 
mathematics morphological method for image segmentation based on region processing, has many advantages.The result of watershed algorithm is global segmentation, border
closure and high accuracy. It can achieve one-pixel wide, connected, closed and exact location of outline. Then we perform the RGB separation for the processed images. Features 
are the information extracted from images in terms of numerical values that are difficult to understand and correlate by human. Here we use LBP and VAR operators to characterize 
the texture of retina background. While calculating LBP and VAR we didn’t consider the optic disc and blood vessels.

### Classification
After the feature extraction is done we use support vector machine (SVM) for classification of these into DR and NonDR. Support-vector networks are supervised learning models
with associated learning algorithms that analyze data used for classification and regression analysis. An SVM model is a representation of the examples as points in space, mapped
so that the examples of the separate categories are divided by a clear gap that is as wide as possible. According to the SVM algorithm we find the points closest to the line from
both the classes. These points are called support vectors. Now, we compute the distance between the line and the support vectors. This distance is called the margin. The 
hyperplane for which the margin is maximum is the optimal hyperplane.
