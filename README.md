# facedetection-in-opencv
it's simple haarcascade coding about face detection
import cv2

face_cascade=cv2.CascadeClassifier(r"C:\Users\AMRIX\haarcascade_frontalface_default.xml")
img=cv2.imread(r"C:\Users\AMRIX\Downloads\girlz.jpg")

gray_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)

faces=face_cascade.detectMultiScale(gray_img,scaleFactor=1.5,minNeighbors=5)
print(faces)

for x,y,w,h in faces:
    img=cv2.rectangle(img,(x,y),(x+w,y+h),(255,0,0),20)

img=cv2.resize(img,(1000,700))
#resized=cv2.resize(img,(0,0), fx=0.1,fy=0.1)
#resized=cv2.resize(img,(int(img.shape[1]/2, int(img.shape[0]/2))))

cv2.imshow("GRay",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
