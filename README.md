>>> import cv2
>>>
#Get user Supplied values
imagePath = sys.argv (1)
cascPath = sys.argv(2)
#Create the haar cascade
faceCascade = cv2.cascade Classifier (casc path)

#Read the image
Image = cv2.imread (imagepath)
gray = cv2.cvtcolor(image, cv2.color_BGR@GRAY)
#detect faces in the image
Faces = faceCascade. detectMultiscale(
         Gray,
          Scalefactor =1.1,
          minNeighbors = 5,
          minSize = (30, 30),
          flags =  cv2.cv.cv_HAAR_SCALE_IMAGE
)
Print  “Found {0} faces !” .format (len(faces))
#Draw a rectangle around the faces
for (x, y, w, h) in faces:
                 cv2.rectangle(image,   (x, y),  (x+w, y+h),  (0,  255,  0),  2)
cv2.imshow(“Faces found”,  image)
cv2.waitkey(0)
