# lane-detection
We're doing Lane detection to identify the path for a Self Driving Car, 
whether it should move away from it or follow it. 
We used three main function in lane-detection project.

First,Gaussian & Filter2D :
1- import cv2: This line imports the OpenCV library, which we will use for computer vision 
      tasks.
2- import numpy as np: This line imports the NumPy library, which we will use for numerical          
      computations.
3- image = cv2.imread(r'C:\Users\kapitoo\Downloads\apple.jpg', 1): This line reads an image file named "apple.jpg" located in the "Downloads" folder of the current user. The image is read 
      as grayscale, and the 1 argument tells OpenCV to convert the image to grayscale.
4- cv2.imshow('Original Image', image): This line displays the original image in a window called "Original Image".
5- cv2.imshow('Blurred Image', blurred_image): This line displays the blurred image in a window 
      called "Blurred Image".
6- cv2.waitKey(0): This line waits for the user to press a key. The 0 argument tells OpenCV to 
      wait indefinitely.
7- cv2.destroyAllWindows(): This line destroys all windows that were created by OpenCV.
8- def filter2d(image, kernel):: This function applies a 2D filter to an image using a kernel. 
      The kernel is a small matrix that slides over the image, applying a weighted average of    
         the pixels in the image. The weights are defined by the kernel itself.
9- def sobel_operator(image):: This function applies the Sobel operator to an image. The Sobel 
      operator is a computer vision technique used to detect edges in images.
10-def convolve(image, kernel):: This function applies convolution to an image using a kernel. 
      Convolution is a computer vision technique used to detect edges in images.
11-def canny_edge_detection(image, low_threshold, high_threshold):: This function applies Canny 
      edge detection to an image using low and high thresholds. Canny edge detection is a   
        computer vision technique used to detect edges in images.
12-image = cv2.GaussianBlur(image, (5, 5), 0): This line applies Gaussian blur to the image 
      using a kernel with a standard deviation of 5. Gaussian blur is a computer vision 
        technique used to reduce noise in images.
13-gradient_magnitude, gradient_direction = sobel_operator(blurred_image): This line computes 
      the gradient magnitude and direction of the blurred image using the Sobel operator.
14-edges = non_maximum_suppression(gradient_magnitude, gradient_direction): This line applies 
      non-maximum suppression to the gradient magnitudes and directions to remove edges that are not strong enough. 
15-edges = hysteresis_thresholding(edges, low_threshold, high_threshold): This line applies 
      hysteresis thresholding to the edges to remove edges that are not strong enough.
16-return edges: This line returns the detected edges.

In summary,    
         The code first reads an image and displays it in two windows: "Original Image" and "Blurred Image". Then, it applies Gaussian blur to the image to reduce noise. Next, it applies the Sobel operator to the blurred image to detect edges. The Sobel operator computes the gradient magnitude and direction of the image. Then, it applies



Second,Canny edge detection :
1-import cv2: This line imports the OpenCV library, which we will use for computer vision tasks.
2-import numpy as np: This line imports the NumPy library, which we will use for numerical computations.
3-image = cv2.imread(r'C:\Users\kapitoo\Downloads\apple.jpg', 1): This line reads an image file named "apple.jpg" located in the "Downloads" folder of the current user. The image is read as    
       grayscale, and the 1 argument tells OpenCV to convert the image to grayscale.
4-cv2.imshow('Original Image', image): This line displays the original image in a window called "Original Image".
5-cv2.imshow('Canny Edges', canny_edges): This line displays the Canny edges image in a window called "Canny Edges".
6-cv2.waitKey(0): This line waits for the user to press a key. The 0 argument tells OpenCV to wait indefinitely.
7-cv2.destroyAllWindows(): This line destroys all windows that were created by OpenCV.
8-def sobel_operator(image):: This function applies the Sobel operator to an image. The Sobel operator is a computer vision technique used to detect edges in images.
9-def convolve(image, kernel):: This function applies convolution to an image using a kernel. Convolution is a computer vision technique used to detect edges in images.
10-def canny_edge_detection(image, low_threshold, high_threshold):: This function applies Canny edge detection to an image using a low threshold value and a high threshold value. Canny edge           
       detection is a computer vision technique used to detect edges in images.
11-image = cv2.GaussianBlur(image, (5, 5), 0): This line applies Gaussian blur to the image using a kernel with a standard deviation of 5. Gaussian blur is a computer vision technique used to reduce noise in images.
12-gradient_magnitude, gradient_direction = sobel_operator(blurred_image): This line computes the gradient magnitude and direction of the blurred image using the Sobel operator.
13-edges = non_maximum_suppression(gradient_magnitude, gradient_direction): This line applies non-maximum suppression to the gradient magnitudes and directions to remove edges that are not strong enough.
14-edges = hysteresis_thresholding(edges, low_threshold, high_threshold): This line applies hysteresis thresholding to the edges to remove edges that are not strong enough.
15-return edges: This line returns the detected edges.

In summary,
         The code applies Canny edge detection to an image and displays the original image and the detected edges in separate windows. The canny_edge_detection function applies a series of steps to detect edges in an image, including Gaussian blurring, gradient computation using Sobel operators, non-maximum suppression, and edge tracking by hysteresis. The function returns the edges of the image as a binary image (0/255).



Finally,Main function:
1- we imported two libraries, cv2 and numpy.
2- we loaded the video and applied the Gaussian blur function to make the images in the video clearer.
3-we converted the video from BGR to HSV to recognize the color of the lane (yellow).We specified the H(Hue), S(Saturation), V(Value) for the desired color.
4-we used Canny function to detect edges.
5- we used the Hough Lines P library to detect lines and specified the parameters for the line  using position(r) and angle(phi).
6-we highlighted the detected line in red for visibility.
7-we displayed the processed video.

In summary,
        The code applies Gaussian Blur function then convert video into HSVto detect line then Canny function and Hough Line P then displayed output video 
 
