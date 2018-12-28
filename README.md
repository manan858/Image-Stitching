# Image-Stitching
Implementation of image stitching and panorama construction using Python and OpenCV.

* To construct image panorama, computer vision and image processing techniques are utilized such as: keypoint detection and local invariant descriptors; keypoint matching; RANSAC; and perspective warping.
* Since there are major differences in how OpenCV 2.4.X and OpenCV 3.X handle keypoint detection and local invariant descriptors (such as SIFT and SURF), I’ve taken special care to provide code that is compatible with both versions (provided that you compiled OpenCV 3 with opencv_contrib  support, of course).

## Image stitching algorithm
* **Step #1:** Detect keypoints (DoG, Harris, etc.) and extract local invariant descriptors (SIFT, SURF, etc.) from the two input images.
* **Step #2:** Match the descriptors between the two images.
* **Step #3:** Use the RANSAC algorithm to estimate a homography matrix using our matched feature vectors.
* **Step #4:** Apply a warping transformation using the homography matrix obtained from Step #3.
 
### Usage
* python stitch.py --first images/FIRST_IMAGE.png --second images/SECOND_IMAGE.png
