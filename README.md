import cv2 as cv
import numpy as np
img = cv.imread('vf7.jpg')
assert img is not None, "Không tìm thấy ảnh vf7.jpg"
print("Giá trị pixel tại (200,100):", img[200,100])
img[200,100] = [255,255,255]
roi = img[280:500, 350:500]   # ROI của bạn
cv.imshow("ROI", roi)
h, w = roi.shape[:2]
img[150:150+h, 300:300+w] = roi
img_no_red = img.copy()
img_no_red[:,:,2] = 0
BLUE = [255,0,0]
border = cv.copyMakeBorder(
    img_no_red, 20,20,20,20,
    cv.BORDER_CONSTANT, value=BLUE
)
cv.imshow("VF7 ", border)
cv.waitKey(0)
cv.destroyAllWindows()
