Drowsiness and Yawn detection with voice alert using Dlib
Simple code in python to detect Drowsiness and Yawn and alert the user using Dlib.

Dependencies
Python 3
opencv
dlib
imutils
scipy
numpy
argparse


Run
Python3 drowsiness_yawn.py -- webcam 0		//For external webcam, use the webcam number accordingly

Setups
Change the threshold values according to your need
EYE_AR_THRESH = 0.3
EYE_AR_CONSEC_FRAMES = 30
YAWN_THRESH = 10`	//change this according to the distance from the camera

Note : If you get espeak not recognized as an error then download from espeak Website : https://sourceforge.net/projects/espeak/
After install in your local machine set the PATH to it
