# Installing OpenCV on Windows for C++

# Step 1 

Go to https://github.com/opencv/opencv and download the Lastest Release

Extract Files to local drive e.g. D\:

<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/Release.jpg" width="1280">


# Step 2 

Add bin folder to the Enviornmet Variables path 

D:\opencv\build\x64\vc15\bin

Restart computer 

<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/EnvironmentVariables.jpg" width="1280">


# Step 3 

Create a New Visual Studio project C++ console. 

Set the platform target to x64

<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/TarrgetPlatform.jpg" width="1280">


# Step 4

Add Directories by going to Project-Properties-Configuration Properties- 

    VC++ Directories
        1. Add Build Directories: D:\opencv\build\include
        2. Add Library Directories: D:\opencv\build\x64\vc15\lib
    Linker Input 
        3. Add Linker input: opencv_world450d.lib
           d for debug without d for release 

<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/VccDirectories.jpg" width="1280">
<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/Linker.jpg" width="1280">



# Step 5

Run test code. First add the lena image to the Source Files
* In this example the image is placed in a new folder by the name Resources therefore the path is "Resources/test.png"

        #include <opencv2/imgcodecs.hpp>
        #include <opencv2/highgui.hpp>
        #include <opencv2/imgproc.hpp>
        #include <iostream>

        using namespace cv;
        using namespace std;


        /////////////////  Images  //////////////////////

        void main() {

            string path = "Resources/test.png";
            Mat img = imread(path);
            imshow("Image", img);
            waitKey(0);

        }

<img src="https://github.com/murtazahassan/opencv-cpp-course/blob/main/ExtraImages/Test.jpg" width="1280">
