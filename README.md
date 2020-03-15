# Android app to measure your weight
An android app that measures your body dimensions and uses it to calculate your weight

Smartphones are all over the place! The time has passed for tools to be needed to measure height and weight. Our application can measure a person’s height and waist width with just a smartphone and estimate his or her weight based on the data collected.Then we are passing the data collected to the server which will estimate the weight of the person and send back to the application.

### Project Setup Permissions ###  
The architecture consists of 2 systems. The configurations and functions are described below:  

**Android Device**  
- Make Model: OnePlus 5T
- OS: Android 7.0 (Nougat)  

**Cloud Server**  
Setup on a different Network, located on the cloud. An Amazon Web Services is used.  
- OS: Linux  
- RAM: 2gb DDR4  

The android device communicated with the server using a bidirectional SSH.  

### Architecture Setup ###  
- Server and android application are using GET and POST responses in JSON.  
- Cloud server has the Regression algorithm which receives the JSON response via the GET method and predicts the weight. This prediction is sent back to the Android mobile device using POST method.  

### Our Implementation ###  
We have implemented the project in different phases where in each phase we will be trying to overcome the hurdles which we are facing.  
## Phase 1 ##  
First of what we worked on is to gather the information for the idea to work and achieve what we are doing and to overcome any problems which we are facing and try to get as much as good accuracy as possible. So the problem we faced was the body structure of men and women are different which would affect our weight estimation (because usually men weighs more than women).So, our accuracy would be affected if we cannot differentiate between the gender of a person. So, to overcome that we collected following information from user (such as person’s age and gender) to predict person’s weight accurately. Collecting this information we created the main screen (front-end part) of the application as follows:
- On this first screen as shown in figure 1 we are getting the person’s name, age and gender using some tools in android studio.


## Phase 2 ##  
In Phase 2, we are trying to take the measurements of the person using the camera.  
- Here the screen will contain multiple buttons and one user input field where the user has to input the height of the camera otherwise he/she cannot proceed any further.
- The only factor which we need to consider to calculate person’s height is at what height the camera is from the ground. We are using this formula to calculate the person’s height and depth (at what distance person is standing from the camera), using the camera height. It is as shown in figure 5 [2].
- All the other things can be measured using these measurements by using sensors like gyroscope, accelerometer and magnetometer which are inbuilt in the phone.
- Above screenshots will help you understand what actually the application is doing and how all the measurements are being taken.
- First when we set the camera height, we are positioning the marker at the person’s feet and then clicking ’Find Depth’ button to find the distance between the person and the camera. Straight after that we will point the camera at the person’s head and click the button ’Get height’ and we will get height using the logic explained above. 
- Also, for getting the width of person we are taking the pointer to the starting point and clicking on the button ’find length’ then we are taking the pointer to the end of the person’s waist and then again clicking on the button will get you the width of the person (whatever you are considering as waist like some person could also take shoulders to measure the width.)
- After we get all the required measurements we click on the ’Calculate Weight’ button which will send all the data to the server. 


## Phase 3 ##  
In Phase 3, we first tried to calculate the weight using the general formula. But that formula was giving us very inaccurate results, so that’s why we switched to create a machine learning model which would have accurate  data sets (probably 1000’s of rows of these data) which will then help us to calculate the weight with more  efficiency. We are running the machine learning model on the server side which will calculate the result required and transfer it back to the android application.  
- We are creating a linear regression model where we have trained this model using some data sets (approx. 10,000 rows) which contains the data of person’s gender and their height.  
- When the application sends person’s data to the server we try to predict its weight using the machine learned model which will predict the person’s approximate weight.
- So now the calculated weight will be send back by server to the application.

So this way our application works and try to estimate the person’s weight as accurately as possible.


