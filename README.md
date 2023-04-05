# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: 
Read the gray and color image using imread() 
### Step2:
Print the image using imshow().
### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.
### Step4:
cv2.equalize() is used to transform the gray image to equalized form.
### Step5:
The Histogram of gray scale image and color image is shown.

## Program:
### Developed By:Sanjay Kumar S S
### Register Number:212221240048
import cv2
import matplotlib.pyplot as plt

### Write your code to find the histogram of gray scale image and color image channels.
```
im = cv2.imread("op.png",0)
cv2.imshow("bw.png",im)
cv2.waitKey(0)
cv2.destroyAllWindows()

hist = cv2.calcHist([im],[0],None,[256],[0,255])
# Colour Image
im_c = cv2.imread("op.png",1)
cv2.imshow("clr",im_c)
cv2.waitKey(0)
cv2.destroyAllWindows()

hist_c = cv2.calcHist([im_c],[1],None,[256],[0,255])
```
### Display the histogram of gray scale image and any one channel histogram from color image
```
plt.figure()
plt.title("Histogram of B/W Image")
plt.xlabel("GrayScale Values")
plt.ylabel("Pixel Count")
plt.stem(hist)
plt.show()

plt.figure()
plt.title("Histogram of CLR Image")
plt.xlabel("GrayScale Values")
plt.ylabel("Pixel Count")
plt.stem(hist_c)
plt.show()
```
### Write the code to perform histogram equalization of the image. 
```
equ = cv2.equalizeHist(im)
cv2.imshow("op1",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()
hist1 = cv2.calcHist([equ],[0],None,[256],[0,255])
plt.figure()
plt.title("Equalized Histogram of B/W Image")
plt.xlabel("GrayScale Values")
plt.ylabel("Pixel Count")
plt.stem(hist1)
plt.show()
```
## Output:
### Input Grayscale Image and Color Image

<img src='https://user-images.githubusercontent.com/93427246/229993154-170ab310-a90d-4126-8a72-858b07b95f4e.png'>

<img src='https://user-images.githubusercontent.com/93427246/229993351-5f401c5b-9c1e-4855-ba16-87e1d24c5398.png'>


### Histogram of Grayscale Image and any channel of Color Image
<br>
<img src='https://user-images.githubusercontent.com/93427246/229994183-077c0398-00ce-4f95-a0e1-359e3ab199d3.png'>

<br>
<img src='https://user-images.githubusercontent.com/93427246/229994282-dd8a7c38-0b3b-4eb7-a27d-2bc270b387e9.png'>

<br>

### Histogram Equalization of Grayscale Image
<br>
<img src='https://user-images.githubusercontent.com/93427246/229995051-34283ba8-304f-4baa-8115-f7e667a13f3c.png'>

<br>
<br>
<img src='https://user-images.githubusercontent.com/93427246/229995429-0726a111-6fc4-4ad1-9799-4da154016de1.png'>


<br>

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
