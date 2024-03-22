# U-Net-based-Catheter-Segmentation

In this project, cardiac catheters are segmented using U-Net based deep learning architectures from X-Ray images obtained through
a fluoroscopic sequence of the chest area. Original images along with their respective binary masks are used to train a U-Net model to segment the catheter
and then the model is tested using different accuracy metrics conventionally used in deep learning.

Images are taken from a fluoroscopic sequence and labelled using 3DSlicer to create a training and validation set for the model. The U-Net model is loaded from Keras and Tensorflow's own 
library with an 'efficientnetb2' backbone that serves in aided image classification in transfer learning where it provides the U-Net with pretrained weights. To improve the computational efficiency, 
the images are preprocessed before being fed into the model as input. The preprocessing techniques include resizing/rescaling the images to a size of 256x256 pixels each, and then normalizing them by 
dividing them by 255 to get the images on a 0-1 scale. Rescaling allows for simpler processing by reducing the number of pixels to be processed and normalization allows for faster convergence of the 
deep learning model when the input is adjusted to have zero mean and unit variance. This optimizes the model’s efficiency in working with our data.

Once training is completed and basic evaluation metrics are analyzed, a predicted segment mask of the cardiac catheter is also obtained. Since this segmentation problem was computationally implemented 
as a classification problem, each pixel is classified according to the ground truth mask of the catheter and then the output classification, or so called ‘segmentation’, is seen as the segmented mask.

![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/060046b8-49f5-4116-a020-0d4937930610)
![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/90334c92-f6d4-422a-b269-86e2f1b97127)
![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/350b40ec-14d4-4159-962c-7955b7e4cc28)

![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/d402437f-140d-4da6-b6cb-ee0527c075e6)
![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/632f764c-d29e-410a-b541-3bad96616442)
![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/a8459579-589a-46ed-87a0-29244c49bac7)
![image](https://github.com/muhammadsanaullah/U-Net-based-Catheter-Segmentation-/assets/45742695/f49d46ec-9406-4731-af02-43089f1322b3)

The model implemented in this project overall showed very promising results. Although larger number of images are generally used in deep learning based datasets, it can be seen the U-Net model worked well 
even for a small dataset of 234 images. The model can further be tested for more images as well and for different angles, which is common for fluoroscopic procedures. Ongoing work on this project includes
additional labelling to create a larger dataset for training and testing, which can account for other types of interventional cardiac devices, as well as developing different variation model architectures based on the UNet. 
