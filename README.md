# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

## Program:
### Developed By: JAVITH M
### Register Number: 212222110014

### i) Read and display the image
```python
import cv2
image=cv2.imread('re.jpg',1)
image=cv2.resize(image,(400,300))
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![image](https://github.com/user-attachments/assets/c0139dd6-b0d2-4164-83ad-539a5a4aa9e7)

### ii)Write the image
```python
import cv2
image=cv2.imread('re.jpg',0)
cv2.imwrite('img.jpg',image)
```
### Output:

![Screenshot 2024-08-23 192414](https://github.com/user-attachments/assets/a9ba47e2-58aa-414f-b9b1-673693b40558)

### iii)Shape of the Image
```python
import cv2
image=cv2.imread('re.jpg',1)
print(image.shape)
```
### Output:

![Screenshot 2024-08-23 192505](https://github.com/user-attachments/assets/eacfcffd-f320-4d7a-8062-b32c54090a70)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('re.jpg',1)
image=cv2.resize(image,(400,300))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-08-23 192743](https://github.com/user-attachments/assets/82b625de-3195-468b-a598-62a15a212abf)

### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('re.jpg',1)
image=cv2.resize(image,(500,400))
tag =image[200:300,110:210]
image[110:210,200:300] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 204927](https://github.com/user-attachments/assets/b336669d-72e3-44f3-9083-cf3e472ada57)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('re.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 205800](https://github.com/user-attachments/assets/d1ea97d4-08e7-4231-906f-6ec24ce49afb)

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('re.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 210114](https://github.com/user-attachments/assets/524cc73a-7be6-469d-b66d-debe53eb4ca2)

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('re.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 210213](https://github.com/user-attachments/assets/00d64d81-8d23-4834-9f59-d8d31eeaeec7)

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('re.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 210636](https://github.com/user-attachments/assets/1f975ded-869d-41a4-8fb5-8d5541070e43)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("re.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:

![Screenshot 2024-08-23 210921](https://github.com/user-attachments/assets/b2f1fe59-f074-435e-b6ce-c2bb6c4968c1)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
