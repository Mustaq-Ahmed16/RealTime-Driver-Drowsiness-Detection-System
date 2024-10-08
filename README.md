# Real-Time-Drowsiness-Detection-System

Drowsiness detection is a safety technology that can prevent accidents that are caused by drivers who fell asleep while driving. The objective of this project is to build a drowsiness detection system that will detect drowsiness through the implementation of computer vision system that automatically detects drowsiness in real-time from a live video stream and then alert the user with an alarm notification.

## Motivation 
According to the National Highway Traffic Safety Administration, every year about 100,000 police-reported crashes involve drowsy driving. These crashes result in more than 1,550 fatalities and 71,000 injuries. The real number may be much higher, however, as it is difficult to determine whether a driver was drowsy at the time of a crash. So, we tried to build a system, that detects whether a person is drowsy and alert him.

## Built With

* [OpenCV Library](https://opencv.org/) - Most used computer vision library. Highly efficient. Facilitates real-time image processing.
* [imutils library](https://github.com/jrosebr1/imutils) -  A collection of helper functions and utilities to make working with OpenCV easier.
* [Dlib library](http://dlib.net/) - Implementations of state-of-the-art CV and ML algorithms (including face recognition).
* [scikit-learn library](https://scikit-learn.org/stable/) - Machine learning in Python. Simple. Efficient. Beautiful, easy to use API.
* [Numpy](http://www.numpy.org/) - NumPy is the fundamental package for scientific computing with Python. 


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

1. Install and set up Python 3.
1. Install [cmake](https://github.com/Kitware/CMake/releases/download/v3.13.3/cmake-3.13.3-win64-x64.zip) in your system

## Running the application

1. Clone the repository. 

    ```
    git clone https://github.com/AnshumanSrivastava108/Real-Time-Drowsiness-Detection-System
    ```
    
1. Move into the project directory. 

    ```
    cd Real-Time-Drowsiness-Detection-System
    ```
 
1. (Optional) Running it in a virtual environment. 

   1. Downloading and installing _virtualenv_. 
   ```
   pip install virtualenv
   ```
   
   2. Create the virtual environment in Python 3.
   
   ```
    virtualenv -p C:\Python37\python.exe test_env
   ```    
   
   3. Activate the test environment.     
   
        1. For Windows:
        ```
        test_env\Scripts\Activate
        ```        
        
        2. For Unix:
        ```
        source test_env/bin/activate
        ```    

1. Install all the required libraries, by installing the requirements.txt file.

    ```
    pip install -r requirements.txt
    ```
    
1. Installing the dlib library.
     
    1. If you are using a Unix machine, and are facing some issues while trying to install the dlib library, follow [this guide](https://gist.github.com/ageitgey/629d75c1baac34dfa5ca2a1928a7aeaf).  
    
    1. If you are using a Windows machine, install cmake and restart your terminal. 
    
1. Run the application.

    ```
    python Real-Time-Drowsiness-Detection-System.py --shape-predictor shape_predictor_68_face_landmarks.dat --alarm Alert.wav
    ```

## Alogorithm

1. Capture the image of the driver from the camera.
2. Send the captured image to haarcascade file for face detection.
3. If the face is detected then crop the image consisting of the face only. If the driver is distracted then a face might not be detected, so play the buzzer.
4. Send the face image to haarcascade file for eye detection.
5. If the eyes are detected then crop only the eyes and extract the left and right eye from that image. If both eyes are not found, then the driver is looking sideways, so sound the buzzer.
6. The cropped eye images are sent to the hough transformations for detecting pupils, which will determine whether they are open or closed.
7. If they are found to be closed for five continuous frames, then the driver should be alerted by playing the buzzer.

### Project Screenshots
When the Driver is Drowsy:
![Screenshot 2024-09-15 152935](https://github.com/user-attachments/assets/4852add9-a0ea-4269-a67f-e5132a23fe3f)
When the Driver is Yarny:
![Screenshot 2024-09-15 152959](https://github.com/user-attachments/assets/5dc8d333-f68d-4a24-a330-a9f127fa6f96)
When the driver is looking right and left:
![Screenshot 2024-09-15 153018](https://github.com/user-attachments/assets/e4020542-2566-4197-9693-0af0d2a5e068)

For More Info, you can refer this : https://pyimagesearch.com/2017/05/08/drowsiness-detection-opencv/
### Dependencies
Python 3
opencv
dlib
imutils
scipy
numpy
argparse

### Run
```
Python3 drowsiness_yawn.py -- webcam 0		//For external webcam, use the webcam number accordingly
```

### Setups
Change the threshold values according to your need
```
EYE_AR_THRESH = 0.3
EYE_AR_CONSEC_FRAMES = 30
YAWN_THRESH = 10`	//change this according to the distance from the camera
```

## Note :
If you get espeak not recognized as an error then download from espeak Website : https://sourceforge.net/projects/espeak/
After install in your local machine set the PATH to it

## References

IEEE standard Journal Paper,

[1]	Facial Features Monitoring for Real Time Drowsiness Detection by Manu B.N, 2016 12th International Conference on Innovations in Information Technology (IIT) [Pg. 78-81] (https://ieeexplore.ieee.org/document/7880030)

[2]	Real Time Drowsiness Detection using Eye Blink Monitoring by Amna Rahman Department of Software Engineering Fatima Jinnah Women University 2015 National Software Engineering Conference (NSEC 2015) (https://ieeexplore.ieee.org/document/7396336)

Websites referred:

1.	https://www.codeproject.com/Articles/26897/TrackEye-Real-Time-Tracking-Of-Human-Eyes-
2.	https://realpython.com/face-recognition-with-python/
3.	https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv
4.	https://www.pyimagesearch.com/2017/04/10/detect-eyes-nose-lips-jaw-dlib-opencv
5.	https://www.codeproject.com/Articles/26897/TrackEye-Real-Time-Tracking-Of-HumanEyesUsing-a
6.	https://docs.opencv.org/3.4/d7/d8b/tutorial_py_face_detection.html
7.	https://www.learnopencv.com/training-better-haar-lbp-cascade-eye-detector-opencv/
