# EX-1 COLOR_CONVERSIONS_OF-IMAGE
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
```
 Developed By: Balachandran S
 Register Number: 212222100008
```

### i) Read and display the image
```python
    import cv2
    image=cv2.imread('NEW ONE.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('display',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/1d031ae7-8812-4e4b-ade9-8cc78050544c">
<br>

### ii)Write the image
```python
    import cv2
    image=cv2.imread('NEW ONE.jpg',0)
    cv2.imwrite('NOPE.jpg',image)
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/e601465b-9682-4683-a528-fa496463bf09">
<br>

### iii)Shape of the Image
```python
    import cv2
    image=cv2.imread('NEW ONE.jpg',1)
    print(image.shape)
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/50765677-ebeb-4c79-9fdc-52544e2f55dd">
<br>

### iv)Access rows and columns
```python
     import random
     import cv2
     image=cv2.imread('NEW ONE.jpg',1)
     image=cv2.resize(image,(400,400))
     for i in range (150,200):
       for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
     cv2.imshow('part image',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/70deb798-953a-4c8f-809d-1a21ebb5aa70">
<br>

### v)Cut and paste portion of image
```python
     import cv2
     image=cv2.imread('NEW ONE.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/15fff874-ba9e-48e4-9c7a-0b45633731aa">
<br>

### vi) BGR and RGB to HSV and GRAY
```python
    import cv2
    img = cv2.imread('NEW ONE.jpg',1)
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
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/488cd41e-a3ee-4c5d-b261-c789f0cc67e4">
<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('NEW ONE.jpg')
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
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/ea3f4953-4df9-471e-ae4a-e9242e0cdbda">
<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('NEW ONE.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/29ebbe17-d4b8-45dc-84d4-82e56b1b93b4">
<br>

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('NEW ONE.jpg',1)
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
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/860e80d5-8664-4586-b891-0607478ab71b">
<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("NEW ONE.jpg",1)
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
#### OUTPUT:
<br>
<img src="https://github.com/Balachandran143/COLOR_CONVERSIONS_OF-IMAGE/assets/118886489/f1f47bb4-d6b1-41ef-87d1-174f211afbf3">
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







