# Detection-of-DR-using-LBP

## Proposed System
![Screenshot 2022-01-01 192222](https://user-images.githubusercontent.com/93415381/147852137-8780683b-4b66-40cc-8fab-54acf6703604.png)

### Preprocessing
We use images from different sources, the size of image varies. Hence we need to rescale the images using length of horizontal diameter of fundus as reference. Here Bicubic 
interpolation is used for resizing of image. The output pixel is weighted average of pixels in nearest 4*4 neighbourhood. After rescaling, to remove noise we use Median filter 
using 3*3 neighbourhood.
