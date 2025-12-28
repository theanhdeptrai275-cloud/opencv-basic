# opencv-basic
Các ví dụ OpenCV cơ bản bằng Python cho sinh viên
import cv2

# Đường dẫn ảnh
path = "D:/cat22.jpg"

# Đọc ảnh
image = cv2.imread(path)

# Resize ảnh gốc về 300x300
image_resized = cv2.resize(image, (300, 300))

# Chuyển ảnh sang ảnh xám
gray_image = cv2.cvtColor(image_resized, cv2.COLOR_BGR2GRAY)

# Cân bằng lược đồ xám
equalized_image = cv2.equalizeHist(gray_image)

# Lọc ảnh bằng bộ lọc trung bình (kernel 5x5)
mean_filtered = cv2.blur(equalized_image, (5, 5))

# Hiển thị ảnh
cv2.imshow("anh goc resize", image_resized)
cv2.imshow("anh xam", gray_image)
cv2.imshow("Sau can bang luoc do", equalized_image)
cv2.imshow("Sau loc trung binh", mean_filtered)

# Lưu ảnh
cv2.imwrite("D:/cat22_resized.jpg", image_resized)
cv2.imwrite("D:/cat22_gray.jpg", gray_image)
cv2.imwrite("D:/cat22_equalized.jpg", equalized_image)
cv2.imwrite("D:/cat22_filtered.jpg", mean_filtered)

cv2.waitKey(0)
