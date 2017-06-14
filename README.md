## Advanced Lane Finding
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


Short Overview of the  goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


# Camera Calibration

Open CV is used to detect 9x6 chessboard pattern. If 9x6 chessboard pattern fails a retry with 9x5 is started. This was applyed to all Calibration Images:


    camera_cal\calibration1.jpg
    


![png](readme_images/output_3_1.png)


    camera_cal\calibration10.jpg
    


![png](readme_images/output_3_3.png)



![png](readme_images/output_3_4.png)


    camera_cal\calibration11.jpg
    


![png](readme_images/output_3_6.png)



![png](readme_images/output_3_7.png)


    camera_cal\calibration12.jpg
    


![png](readme_images/output_3_9.png)



![png](readme_images/output_3_10.png)


    camera_cal\calibration13.jpg
    


![png](readme_images/output_3_12.png)



![png](readme_images/output_3_13.png)


    camera_cal\calibration14.jpg
    


![png](readme_images/output_3_15.png)



![png](readme_images/output_3_16.png)


    camera_cal\calibration15.jpg
    


![png](readme_images/output_3_18.png)



![png](readme_images/output_3_19.png)


    camera_cal\calibration16.jpg
    


![png](readme_images/output_3_21.png)



![png](readme_images/output_3_22.png)


    camera_cal\calibration17.jpg
    


![png](readme_images/output_3_24.png)



![png](readme_images/output_3_25.png)


    camera_cal\calibration18.jpg
    


![png](readme_images/output_3_27.png)



![png](readme_images/output_3_28.png)


    camera_cal\calibration19.jpg
    


![png](readme_images/output_3_30.png)



![png](readme_images/output_3_31.png)


    camera_cal\calibration2.jpg
    


![png](readme_images/output_3_33.png)



![png](readme_images/output_3_34.png)


    camera_cal\calibration20.jpg
    


![png](readme_images/output_3_36.png)



![png](readme_images/output_3_37.png)


    camera_cal\calibration3.jpg
    


![png](readme_images/output_3_39.png)



![png](readme_images/output_3_40.png)


    camera_cal\calibration4.jpg
    


![png](readme_images/output_3_42.png)


    camera_cal\calibration5.jpg
    


![png](readme_images/output_3_44.png)


    camera_cal\calibration6.jpg
    


![png](readme_images/output_3_46.png)



![png](readme_images/output_3_47.png)


    camera_cal\calibration7.jpg
    


![png](readme_images/output_3_49.png)



![png](readme_images/output_3_50.png)


    camera_cal\calibration8.jpg
    


![png](readme_images/output_3_52.png)



![png](readme_images/output_3_53.png)


    camera_cal\calibration9.jpg
    


![png](readme_images/output_3_55.png)



![png](readme_images/output_3_56.png)


# Pipeline

## Distortion-correction application

Distortion correction that was calculated via camera calibration has been applied to each image. 


    camera_cal\calibration1.jpg
    


![png](readme_images/output_5_1.png)



![png](readme_images/output_5_2.png)


    camera_cal\calibration10.jpg
    


![png](readme_images/output_5_4.png)



![png](readme_images/output_5_5.png)


    camera_cal\calibration11.jpg
    


![png](readme_images/output_5_7.png)



![png](readme_images/output_5_8.png)


    camera_cal\calibration12.jpg
    


![png](readme_images/output_5_10.png)



![png](readme_images/output_5_11.png)


    camera_cal\calibration13.jpg
    


![png](readme_images/output_5_13.png)



![png](readme_images/output_5_14.png)


    camera_cal\calibration14.jpg
    


![png](readme_images/output_5_16.png)



![png](readme_images/output_5_17.png)


    camera_cal\calibration15.jpg
    


![png](readme_images/output_5_19.png)



![png](readme_images/output_5_20.png)


    camera_cal\calibration16.jpg
    


![png](readme_images/output_5_22.png)



![png](readme_images/output_5_23.png)


    camera_cal\calibration17.jpg
    


![png](readme_images/output_5_25.png)



![png](readme_images/output_5_26.png)


    camera_cal\calibration18.jpg
    


![png](readme_images/output_5_28.png)



![png](readme_images/output_5_29.png)


    camera_cal\calibration19.jpg
    


![png](readme_images/output_5_31.png)



![png](readme_images/output_5_32.png)


    camera_cal\calibration2.jpg
    


![png](readme_images/output_5_34.png)



![png](readme_images/output_5_35.png)


    camera_cal\calibration20.jpg
    


![png](readme_images/output_5_37.png)



![png](readme_images/output_5_38.png)


    camera_cal\calibration3.jpg
    


![png](readme_images/output_5_40.png)



![png](readme_images/output_5_41.png)


    camera_cal\calibration4.jpg
    


![png](readme_images/output_5_43.png)



![png](readme_images/output_5_44.png)


    camera_cal\calibration5.jpg
    


![png](readme_images/output_5_46.png)



![png](readme_images/output_5_47.png)


    camera_cal\calibration6.jpg
    


![png](readme_images/output_5_49.png)



![png](readme_images/output_5_50.png)


    camera_cal\calibration7.jpg
    


![png](readme_images/output_5_52.png)



![png](readme_images/output_5_53.png)


    camera_cal\calibration8.jpg
    


![png](readme_images/output_5_55.png)



![png](readme_images/output_5_56.png)


    camera_cal\calibration9.jpg
    


![png](readme_images/output_5_58.png)



![png](readme_images/output_5_59.png)


    test_images\straight_lines1.jpg
    


![png](readme_images/output_5_61.png)



![png](readme_images/output_5_62.png)


    test_images\straight_lines2.jpg
    


![png](readme_images/output_5_64.png)



![png](readme_images/output_5_65.png)


    test_images\test1.jpg
    


![png](readme_images/output_5_67.png)



![png](readme_images/output_5_68.png)


    test_images\test2.jpg
    


![png](readme_images/output_5_70.png)



![png](readme_images/output_5_71.png)


    test_images\test3.jpg
    


![png](readme_images/output_5_73.png)



![png](readme_images/output_5_74.png)


    test_images\test4.jpg
    


![png](readme_images/output_5_76.png)



![png](readme_images/output_5_77.png)


    test_images\test5.jpg
    


![png](readme_images/output_5_79.png)



![png](readme_images/output_5_80.png)


    test_images\test6.jpg
    


![png](readme_images/output_5_82.png)



![png](readme_images/output_5_83.png)


## birds-eye view application

OpenCV functions has been used rectify each image to a "birds-eye view". The transform manages Regtion of Interrest implicid with the src and dst transform frames.

The inverse "birds-eye view" transform was also implimentet here (but tested later in the prozessing).


    test_images\straight_lines1.jpg
    


![png](readme_images/output_7_1.png)


    test_images\straight_lines2.jpg
    


![png](readme_images/output_7_3.png)


    test_images\test1.jpg
    


![png](readme_images/output_7_5.png)


    test_images\test2.jpg
    


![png](readme_images/output_7_7.png)


    test_images\test3.jpg
    


![png](readme_images/output_7_9.png)


    test_images\test4.jpg
    


![png](readme_images/output_7_11.png)


    test_images\test5.jpg
    


![png](readme_images/output_7_13.png)


    test_images\test6.jpg
    


![png](readme_images/output_7_15.png)


    camera_cal\calibration1.jpg
    


![png](readme_images/output_7_17.png)


    camera_cal\calibration10.jpg
    


![png](readme_images/output_7_19.png)


    camera_cal\calibration11.jpg
    


![png](readme_images/output_7_21.png)


    camera_cal\calibration12.jpg
    


![png](readme_images/output_7_23.png)


    camera_cal\calibration13.jpg
    


![png](readme_images/output_7_25.png)


    camera_cal\calibration14.jpg
    


![png](readme_images/output_7_27.png)


    camera_cal\calibration15.jpg
    


![png](readme_images/output_7_29.png)


    camera_cal\calibration16.jpg
    


![png](readme_images/output_7_31.png)


    camera_cal\calibration17.jpg
    


![png](readme_images/output_7_33.png)


    camera_cal\calibration18.jpg
    


![png](readme_images/output_7_35.png)


    camera_cal\calibration19.jpg
    


![png](readme_images/output_7_37.png)


    camera_cal\calibration2.jpg
    


![png](readme_images/output_7_39.png)


    camera_cal\calibration20.jpg
    


![png](readme_images/output_7_41.png)


    camera_cal\calibration3.jpg
    


![png](readme_images/output_7_43.png)


    camera_cal\calibration4.jpg
    


![png](readme_images/output_7_45.png)


    camera_cal\calibration5.jpg
    


![png](readme_images/output_7_47.png)


    camera_cal\calibration6.jpg
    


![png](readme_images/output_7_49.png)


    camera_cal\calibration7.jpg
    


![png](readme_images/output_7_51.png)


    camera_cal\calibration8.jpg
    


![png](readme_images/output_7_53.png)


    camera_cal\calibration9.jpg
    


![png](readme_images/output_7_55.png)


    test_images\test6.jpg
    


![png](readme_images/output_7_57.png)


## binary image

A manualy weighted sum of YUV is calculated to sum white and yellow lane information constructive. 
The polar representation of Color in HSV/HLS makes it more complex for handcrafting features right.
Canny was applyed.
I belive that the approach can be much improved /finetuned a lot with a deep lerning insted of handcrafting. 


    test_images\straight_lines1.jpg
    


![png](readme_images/output_9_1.png)


    test_images\straight_lines2.jpg
    


![png](readme_images/output_9_3.png)


    test_images\test1.jpg
    


![png](readme_images/output_9_5.png)


    test_images\test2.jpg
    


![png](readme_images/output_9_7.png)


    test_images\test3.jpg
    


![png](readme_images/output_9_9.png)


    test_images\test4.jpg
    


![png](readme_images/output_9_11.png)


    test_images\test5.jpg
    


![png](readme_images/output_9_13.png)


    test_images\test6.jpg
    


![png](readme_images/output_9_15.png)


# Lane Finding

Two way (with and without convolution) were tested for lane finding. The approch without convolution seems to work a little better on my binarized images.

The inverse "birds-eye view" transform was applyed.


    test_images\straight_lines1.jpg
    


![png](readme_images/output_11_1.png)



![png](readme_images/output_11_2.png)


    test_images\straight_lines2.jpg
    


![png](readme_images/output_11_4.png)



![png](readme_images/output_11_5.png)


    test_images\test1.jpg
    


![png](readme_images/output_11_7.png)



![png](readme_images/output_11_8.png)


    test_images\test2.jpg
    


![png](readme_images/output_11_10.png)



![png](readme_images/output_11_11.png)


    test_images\test3.jpg
    


![png](readme_images/output_11_13.png)



![png](readme_images/output_11_14.png)


    test_images\test4.jpg
    


![png](readme_images/output_11_16.png)



![png](readme_images/output_11_17.png)


    test_images\test5.jpg
    


![png](readme_images/output_11_19.png)



![png](readme_images/output_11_20.png)


    test_images\test6.jpg
    
---

![png](readme_images/output_11_22.png)



![png](readme_images/output_11_23.png)




    test_images\straight_lines1.jpg
    


![png](readme_images/output_13_1.png)


    test_images\straight_lines2.jpg
    


![png](readme_images/output_13_3.png)


    test_images\test1.jpg
    


![png](readme_images/output_13_5.png)


    test_images\test2.jpg
    


![png](readme_images/output_13_7.png)


    test_images\test3.jpg
    


![png](readme_images/output_13_9.png)


    test_images\test4.jpg
    


![png](readme_images/output_13_11.png)


    test_images\test5.jpg
    


![png](readme_images/output_13_13.png)


    test_images\test6.jpg
    


![png](readme_images/output_13_15.png)


# Radius of Curvature

Estimations of the curving and the offset of the middle of the road are calculated and overlayed in the right, upper conner of the image.


    test_images\straight_lines1.jpg
    [ -4.21015301e-05   4.42136653e-02   2.89203095e+02] [  2.37113329e-06  -8.46304226e-03   1.00985010e+03]
    


![png](readme_images/output_16_1.png)


    test_images\straight_lines2.jpg
    [  6.43910763e-06   3.34375499e-02   2.77565579e+02] [ -2.77904484e-05  -1.82876465e-02   1.03400704e+03]
    


![png](readme_images/output_16_3.png)


    test_images\test1.jpg
    [  1.44448689e-04  -2.18289341e-01   4.04011585e+02] [  3.21786599e-04  -4.63637461e-01   1.22697301e+03]
    


![png](readme_images/output_16_5.png)


    test_images\test2.jpg
    [ -3.59973589e-04   5.35787780e-01   1.64868208e+02] [ -2.66260906e-04   4.40178058e-01   9.01678238e+02]
    


![png](readme_images/output_16_7.png)


    test_images\test3.jpg
    [  2.07936560e-04  -4.27330868e-01   5.25658394e+02] [  2.58617227e-04  -4.65865074e-01   1.24020141e+03]
    


![png](readme_images/output_16_9.png)


    test_images\test4.jpg
    [  2.75269743e-04  -3.13522530e-01   4.29291809e+02] [  5.36674650e-04  -6.29016276e-01   1.25567808e+03]
    


![png](readme_images/output_16_11.png)


    test_images\test5.jpg
    [  2.97008843e-04  -2.20339905e-01   3.01677812e+02] [  2.56793913e-04  -4.24944890e-01   1.21166814e+03]
    


![png](readme_images/output_16_13.png)


    test_images\test6.jpg
    [  8.64370887e-06  -2.64051400e-01   5.16562341e+02] [  1.95536189e-04  -4.11241593e-01   1.26145857e+03]
    


![png](readme_images/output_16_15.png)


# Video processing

The the Pipeline is defined here and applyed to the Video.

Due to approaching deadline, the pipeline have not yet been finetuned to the challange videos.

The Pipeline is running at acceptable speed even on older hardware.


