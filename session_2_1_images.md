# Images - Angel Chang 
1. Classification 
1. Semantic segmentation
1. Object detection
1. Instance segmentation 

## Image Classification
Covered in the CNN lecture.

## Semantic Segmentation 
* Label each pixel in the image with a category.
* Train a fully convolutional net to make predictions for pixels all at once.
* In practice, peaple downsample the image with conv layers and then upsample the image.
* Upsample (Unpooling):
	* Nearest neighbor 
	* Bed of nails 
	* Max unpooling: use positions from the pooling layer
	* Learnable upsampling: transpose convolution. Filter moves stride in the output for every one pixel in the input 

## Object Detection
* One solution:
	* Apply CNN to many different crops of the image for classification.
	* Problem: Need to apply CNN to huge number of images
* Region proposals: Selective search to identify regions to contain interesting objects
	* R-CNN: Regions of interest (RoI) from a proposal method (~2k)-> warped image regions -> CNN -> classify the regions 
	* Problem: very slow. Need to do ~2k independent forward passes of the CNN 
* Fast R-CNN: 
	* Run whole image through the CNN and then use the proposal method on the output of the conv features
	* Input image -> conv5 features -> Crop + resize features -> CNN for classification 
	* Faster than R-CNN but the run time is dominated by region proposal
* Faster R-CNN:
	* Insert region proposal network (RPN) to predict proposals from features.
	* Image -> feature map -> RPN -> proposals with boudnig box regression loss and classification loss -> RoI pooling

## Instance Segmentation 
* Mask R-CNN:
	* Similar to R-CNN but adds a small mask network that operates on each RoI.
	* Can also predict human pose 
	* Very good performance 

# Structured Representation of Images
* Scene parse tree: Hierarchical  
* Scene graph: Relational
	* Visual genome project: Objects + relationships  	
	* Object proposals -> graph inference -> relations 
* Language and vision 
	* captioning
	* dense captioning 
	* referring expressions
* Visual questioning and answer (VQA)

### Extending to 3D Representation 
* Surface triangle mesh 
* Multi view 
* Voxels
* Points: PointNet 


