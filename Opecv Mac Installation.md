# Installing OpenCV on Mac for C++

# Step 1 – Install Homebrew

    https://brew.sh/
    Go to the website and copy the link and paste in the terminal to install.

# Step 2 – Install Opencv
  
      Go to terminal and type 
      brew install opencv

# Step 3 – Create New Xcode Project

      Open X code and create a "macOS" - "Command Line Tool" - "C++"
  
# Step 4 – Add Dynamic Libraries

      Right Click Project folder and "Add Files to ..."
      Press forward slash "/" on keyboard to type the folder path
      /usr/local/Cellar/opencv
      open your version folder and go to lib and select all Dynamic Libraries 

# Step 5 – Add Header Search Path

      Select your project folder and go to "Build settings"
      Select All and Combined 
      Search for "Header Search Paths" 
      Double click and enter the path (make sure to change your version)
      /usr/local/Cellar/opencv/4.5.0_5/include/opencv4
      make it recursive



# Step 6 – To enable Resources folder access

     Edit Scheme 
     check "Use custom working director" 
     Select your project folder

Test Code 

       #include <opencv2/imgcodecs.hpp>
       #include <opencv2/highgui.hpp>
       #include <opencv2/imgproc.hpp>
       #include <iostream>

       using namespace cv;
       using namespace std;


       /////////////////  Images  //////////////////////

       int main() {

           string path = "Resources/test.png";
           Mat img = imread(path);
           imshow("Image", img);
           waitKey(0);
           return 0;
       }
       
 
# Step 7 – To enable Camera Access

    File - New - File
    Select "Property List" in "Resources"

    Add new
    Item: NSCameraUsageDescription
    Value: $(PRODUCT_NAME) camera use 

    Open Products folder and right click on the file with your project name and 
    show in finder. 

    Drag your info.plist file to this folder. 


Tesr Code 

      #include <opencv2/imgcodecs.hpp>
      #include <opencv2/highgui.hpp>
      #include <opencv2/imgproc.hpp>
      #include <iostream>

      using namespace cv;
      using namespace std;

      ///////////////// Webcam //////////////////////

      int main() {

           VideoCapture cap(1);
           Mat img;

           while (true) {

           cap.read(img);
           imshow("Image", img);
           waitKey(1);

       }
        return 0;
       }
