import cv2 as cv
import numpy as np
# 1. Load ảnh VF7
img = cv.imread('vf7.jpg')
assert img is not None, "Không tìm thấy ảnh vf7.jpg"
# 2. Pixel
print("Giá trị pixel tại (200,100):", img[200,100])
img[200,100] = [255,255,255]
# 3. Lấy ROI (cắt vùng đầu xe)
roi = img[280:500, 350:500]   # ROI của bạn
cv.imshow("ROI", roi)
# Lấy kích thước ROI
h, w = roi.shape[:2]
# 4. Dán ROI vào 
img[150:150+h, 300:300+w] = roi
# 5. Tắt red channel
img_no_red = img.copy()
img_no_red[:,:,2] = 0
# 6. Viền xanh
BLUE = [255,0,0]
border = cv.copyMakeBorder(
    img_no_red, 20,20,20,20,
    cv.BORDER_CONSTANT, value=BLUE
)
# 7. Hiển thị
cv.imshow("VF7 ", border)
cv.waitKey(0)
cv.destroyAllWindows()
