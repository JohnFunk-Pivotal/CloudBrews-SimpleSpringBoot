# Station 1 - SpringBoot
##Introduction
This exercise will introduce you to the productivity gains of using Spring Boot for your Java project.   First we'll use Spring Boot Initializr to create a template Spring Boot application.  Then we will add a few lines of code to make it a REST endpoint and then we'll push this application to Pivotal Cloud Foundry.

### What is Spring Boot Initializr?
Spring Boot Initializr is a fast way to generate a skeleton application and all the necessary dependencies for a Spring Boot application.   Visit https://start.spring.io/ and switch into the full version to see the types of applications it can create.

## Setup
Start by cleaning up after the last person and making a directory in your Google Compute Engine Console and changing into it.
```
cd ~
rm -rf springdatarest
mkdir springboot
cd springboot
```

## Download the starter files from start.spring.io
```
curl start.spring.io/starter.zip -o demo.zip -d dependencies=web -d javaVersion=1.7
unzip demo.zip
```

## Look around at the code
The project code that Spring Boot Initializr just created for you.  It expanded out to the following directory structure.  Notice the starter template includes Java code, static web templates, and even starter test harnesses for you.
![Tree View of the Application](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/blob/master/TreeViewOfApplication.png "Tree View of the Application")


## Add an examplecontroller class
Execute the command below to download the ExampleController.java file.  If you want to look at the source code look at the ExampleController.java of the root directory of this repo.
```
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/master/ExampleController.java -o src/main/java/com/example/ExampleController.java
```  

##Build the project and run it
```
mvn clean install
java -jar target/demo*.jar
```
## Open the application in a browser window
To open a browser from the Google Compute Engine environment click in the control in the upper left of the console window as shown in the following diagrams:

![CloudFoundrySpace](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/blob/master/OpenBrowser1.png "Open a browser")  
![CloudFoundrySpace](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/blob/master/OpenBrowser2.png "Open a browser")

## Stop the project
Once you see the "hello world" output from the app, stop the project hit CTRL-C in the Google Compute Engine console window.


##Push the application to Pivotal Cloud Foundry
Finally we'll push this application to Pivotal Cloud Foundry, but first we have to login.
```
cf login -a api.run.pivotal.io -u demo1@johnfunk.com -o Channel -s Denver-CloudBrews
cf push bootapp -p target/demo-0.0.1-SNAPSHOT.jar --random-route
```
If you are asked for a password please ask one of the helpers at the station to provide it.

## Login to Cloud Foundry
Open Cloud Foundry in a browser by visiting:  http://run.pivotal.io  
   *username: demo1@johnfunk.com  
   *password:  ask one of the helpers  

##Navigate to the Application in Pivotal Cloud Foundry
First click on the 'Denver-CloudBrews' space as shown below:
![CloudFoundrySpace](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/blob/master/CloudFoundrySpace.png "Space view on PCF")  

Next locate the applicaiton called "bootapp" and click on the link under the ROUTE label as shown below:
![CloudFoundryApps](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/blob/master/CloudFoundryApps.png "Apps view on PCF")

## Congratulations
Congratulations you just built a Spring Boot application on Google Compute Engine and pushed it to Pivotal Cloud Foundry.  Talk to the helper at the station to see what's next!

## Feedback
Please help us improve in the future by giving us feedback on this exercise: [Feedback](http://pivotal.DSUW.sgizmo.com/s3/?station=1)
