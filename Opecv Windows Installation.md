# Installing OpenCV on Windows for C++

# Step 1 

Go to https://github.com/opencv/opencv and download the Lastest Release

Extract Files to local drive e.g. D\:

<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/Release.jpg" width="1280">


# Step 2 

Add bin folder to the Enviornmet Variables path 

D:\opencv\build\x64\vc15\bin

Restart computer 

<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/EnvironmentVariables.jpg" width="1280">


# Step 3 

Create a New Visual Studio project C++ console. 

Set the platform target to x64

<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/TarrgetPlatform.jpg" width="1280">


# Step 4

Add Directories by going to Project-Properties-Configuration Properties- 

    VC++ Directories
        1. Add Build Directories: D:\opencv\build\include
        2. Add Library Directories: D:\opencv\build\x64\vc15\lib
    Linker Input 
        3. Add Linker input: opencv_world450d.lib
           d for debug without d for release 

<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/VccDirectories.jpg" width="1280">
<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/Linker.jpg" width="1280">



# Step 5

Run test code. First add the lena image to the Source Files
* In this example the image is placed in a new folder by the name Resources therefore the path is "Resources/lena.png"

    #include <opencv2/core.hpp>
    #include <opencv2/imgcodecs.hpp>
    #include <opencv2/highgui.hpp>
    #include <iostream>
    using namespace cv;
    using namespace std;

    int main()
    {
        string image_path = "Resources/lena.png";
        Mat img = imread(image_path);
        imshow("Image", img);
        waitKey(0);
    }

<img src="https://github.com/murtazahassan/opencv-c-plus-plus/blob/main/ImagesExtra/Test.jpg" width="1280">
