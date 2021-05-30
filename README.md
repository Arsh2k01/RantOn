# RantOn
Size estimator and Virtual try on
As we have observed in the current e-commerce market, specifically in the fashion sector, there are a lot of returns and dissatisfied customers due to improper size and fit. We aim to solve that issue using certain AI and ML techniques so that shoppers can see if the item fits them or not with just one click and how will it look on them. Our solution uses a combination of computer vision, deep learning, and anthropomorphic science to deduct the positions and measurements of several body points from images taken by the users then matches these to the company’s size chart, previous databases on the size, and their body type. This then suggests the optimum size for the specific product and company. The customer can use the suggested size to demand items of their choice. Further virtual dressing room helps the customer get a feel of the fit and look of the product on their own body type, thus reducing confusion and providing a hassle-free shopping experience.


Size Estimator

We have the height and photo given by the user. 
The photo is sent to the notebook ‘Size Estimator’ and the body point allocation code written using OpenCV and OpenPose is run through it. This gives us the various points on the body basically of the joints. Coordinates of these body points are stored in a list named ‘points’ for future use. 

Since the points obtained don't represent the actual size of the person, we use a contour based model of OpenCV to get the contours of the actual flesh of the person. We then plot the points onto the contour and using an algorithm the nearest contour-point to every body point is calculated. This gives the precise measurement of the person in pixels. Pixels are then converted into centimeters.We drew horizontal and vertical lines onto the contour we got to get the actual extreme points of shoulder, bust, hip and waist. Later these points were used to calculate actual sizes.




![alt text](https://github.com/reshma-avvaru/RantOn/blob/main/arsh4.jpeg)
