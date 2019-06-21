# Summer-Project
This repository consists of the summer project 2019 along with some side projects done during the month of June

VDP.py - This project basically deals with making a virtual drawing pad and drawing various shapes without the use of mouse. The video frames are converted to HSV and is thresholded to filter only the green colour, which will act as the "stylus" for us to draw with. A contour is drawn around the "stylus" and then a centroid is calculated for it, which acts as the point using which drawing will take place. The drawings are printed corresponding to the coordinates of the centroid on the real video on another white window. The color and the size of the paint can be changed using the trackbars provided with the code.

points.py - This project basically deals with controlling the mouse cursor using face gestures. Left eye blink indicates left click, right eye blink indicated right click and moving the tip of the nose will move the mouse cursor. The code first finds facial landmarks on the face using the .dat file provided with the repository. Basically it is used to predict the facial landmarks on the face. Altogether, there are 68 such landmark points on the face, out of which, 34rd(33rd index) is identified as the nose tip, 37-42 identified as the left eye and 43-48 identified as the right eye. Now, the tip of the nose is integrated with the mouse using a library called as pyautogui. The algorithm is coded in such as way that the mouse will move in the direction in which the nose is pointing to. This is achieved using polar coordinates. Basically, angle is calculated for between the two lines, the first line made by the centre of the reference circle in which the nose movement will not be plotted, and the second line is a horizontal line passing from the centre of the reference circle(this circle will be plotted in red on the output screen). 
As for the eyes, the initial part of the code snippet basically calibrates the Eye Aspect Ratio or EAR in short, for left and right eye which is suitable for the person which is using it. The reference for the code wil be the difference between the left eye EAR and the right eye EAR, so that when both the eyes are either open or closed, there wouldn't be any change or click. Rest of the explanation of the code is written in the form of comments.
Coming to the mouth, a sample of 30 iterations of the MAR(Mouth Aspect Ratio) is taken, followed by taking its average. Then those 30 iterations are discarded and then the computed average is compared with the threshold average. If it exceeds the threshold average, then the scroll mode is on and so the user will be able to move the nose up and down for scrolling up and down respectively. The same procedure is applied for swtiching OFF the scrolling mode. 
