# FaceMask-Detection-Machine-Learning
To keep protected from the virus in the midst of a pandemic, 
it's critical to follow Covid 19 instructions. The Facemask Detection System, 
which uses Machine Learning, distinguishes people wearing masks and those who don't, and prints notifications in both cases. 
The 'haar face detection frontal face algorithm' is used to detect faces in this project. 
This system can be used in a variety of closed environments where entering without a mask is prohibited.
This method automates the task of recognizing faces with or without a facemask, greatly reducing manual labor.

Primary tasks - 1. Load images using openCV in Python
                2. Convert images into array with RGB values
                3. After loading, perform Violas Jones Face Detection Algorithm


The project makes use of a Image Processing using OpenCV
OpenCV -  1. Open Source Computer Vision and Machine Learning Softeare Library. It has more than 2500 optimized algorithm.  
          2. The main task of openCV is loading images in Python and converting those into arrays
          3. Each index of array represents(red, green, blue) color pixels which ranged from 0-255
          
Application - Face Detection, Geometric Transformation, Image Thresholding, Smoothening images, Canny edge Detection, Background removals, Image Segmentation

Install openCV
                  pip intall opencv-python 'or' !pip intall opencv-python 
               
Violas Jones algorithm has 4 stagees - 1. Haar Feature
                                       2. Creating integral image
                                       3. Adaboost Training
                                       4. cascading classifier 
 
The Haar frontal face algorithm is used in this project. On every human face, there are certain common traits with darker and brighter regions.
Haar recognises these areas and recognises the face.
