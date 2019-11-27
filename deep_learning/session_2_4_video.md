# Video - Greg Mori 
Human activity recognition.

## Introduction
* AI complete: fully underestand what is happening in the scene 
* Challenges:
	* Large variations in appearance 
	* manual collection of training samples is prohibitive 
	* action vocabularu is not well defined 
* Various types/levels of activities: 
	* gestures
	* actions 	
	* human object detections 
	* interactions
	* group activiries 
* Activity classification    
	* input is a video segment containing only one activity 
* activity detection (localization)
	* temporal level 
	* use binary classifiers
	* activity detection (spatio temporal)
* Activtity prediction/ forcest 
	* early recognition based on the ongoing video 
	* infer future activies/locations based on the current info
* Pipeline for video classification with cnns 
	* traditional approach 
	* spatio-temporal filters for short video segments
	* RNNs 
	

## Action Localization 
* typical representation 
	* bounding box extension to 3D
	* cuboid, axis aligned rectangle at each time step 

* Recurrent net with cnn
* AE for representations 


* VAE + LSTM -> check the image

