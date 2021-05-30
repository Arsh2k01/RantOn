# RantOn
Size estimator and Virtual try on <br />
As we have observed in the current e-commerce market, specifically in the fashion sector, there are a lot of returns and dissatisfied customers due to improper size and fit. We aim to solve that issue using certain AI and ML techniques so that shoppers can see if the item fits them or not with just one click and how will it look on them. Our solution uses a combination of computer vision, deep learning, and anthropomorphic science to deduct the positions and measurements of several body points from images taken by the users then matches these to the company’s size chart, previous databases on the size, and their body type. This then suggests the optimum size for the specific product and company. The customer can use the suggested size to demand items of their choice. Further virtual dressing room helps the customer get a feel of the fit and look of the product on their own body type, thus reducing confusion and providing a hassle-free shopping experience.


## Size Estimator

We have the height and photo given by the user. 
The photo is sent to the notebook ‘Size Estimator’ and the body point allocation code written using OpenCV and OpenPose is run through it. This gives us the various points on the body basically of the joints. Coordinates of these body points are stored in a list named ‘points’ for future use. 

Since the points obtained don't represent the actual size of the person, we use a contour based model of OpenCV to get the contours of the actual flesh of the person. We then plot the points onto the contour and using an algorithm the nearest contour-point to every body point is calculated. This gives the precise measurement of the person in pixels. Pixels are then converted into centimeters.We drew horizontal and vertical lines onto the contour we got to get the actual extreme points of shoulder, bust, hip and waist. Later these points were used to calculate actual sizes.


![alt text](https://github.com/reshma-avvaru/RantOn/blob/main/download.png)


## Virtual Try-On

We are devising a solution to real-life trying on problem with the help of OpenCV Library.
As we start to run the file ‘RantOn_Final.py’ , we give 3 arguments to our system : <Path_of_our_File> <Path_of_the_image_of_the_customer> <Path_of_the_image_of_the_apparel_we_want_to_try_on>
We have three supporting .py file :
	- Apparel.py has functions that deals with the preprocessing of the new apparel we want to try on.
	- Customer.py has functions that deals with the preprocessing of the image of the customer.
	- Join.py has functions which fits and puts the new apparel onto the customer to give a very close real-life apparel 	trying experience. 
Given are the classes of function which are defined in the above mentioned files:

**grabcut():**
Takes the required portion of the customer’s image, and gathers the cutout of the already worn up clothing.

**userPreprocess():**
Breaks up the cutout gathered from the last step into various sections (at the joints) to get a better analysis and size of each & every part at minute stages as well.

**catPreprocess():**
Takes up the new apparel’s flattened image, breaks it and resizes it with the cutout sections of the original clothing. 

**userFit():**
Takes up all the modified sections of the new apparel and places them at their appropriate positions on the image of the customer to get a near to real-life visual of the apparel on the customer







![alt text](https://github.com/reshma-avvaru/RantOn/blob/main/Virtual.png)
