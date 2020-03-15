# Weight_measuring_Android_App
An android app that measures your height and uses it to calculate your weight

Smartphones are all over the place! The time has passed for tools to be needed to measure height and weight. Our application can measure a person’s height and waist width with just a smartphone and estimate his or her weight based on the data collected.Then we are passing the data collected to the server which will estimate the weight of the person and send back to the application.

**Project Setup Permissions**
The architecture consists of 2 systems. The configurations and functions are described below:  
 Android Device  
Make Model: OnePlus 5T
OS: Android 7.0 (Nougat)  
 Cloud Server  
Setup on a different Network, located on the cloud. An Amazon Web Services is used.  
OS: Linux  
RAM: 2gb DDR4  
The android device communicated with the server using a bidirectional SSH.  

**Architecture Setup**  
 Server and android application are using GET and POST responses in JSON.  
 Cloud server has the Regression algorithm which receives the JSON response via the GET method and predicts the weight. This prediction is sent back to the Android mobile device using POST method.  

**Our Implementation**
We have implemented the project in different phases where in each phase we will be trying to overcome the hurdles which we are facing.
**Phase 1**
First of what we worked on is to gather the information for the idea to work and achieve what we are doing and to overcome any problems which we are facing and try to get as much as good accuracy as possible. So the problem we faced was the body structure of men and women are different which would affect our weight estimation (because usually men weighs more than women).So, our accuracy would be affected if we cannot differentiate between the gender of a person. So, to overcome that we collected following information from user (such as person’s age and gender) to predict person’s weight accurately. Collecting this information we created the main screen (front-end part) of the application as follows:
- On this first screen as shown in figure 1 we are getting the person’s name, age and gender using some tools in android studio.

