# Station 1 - SpringBoot
##Introduction
This exercise will introduce you to the productivity gains of using Spring Boot for your Java project.   First we'll use Spring Boot Initializr to create a template Spring Boot applicaiton.  Then we will add a few lines of code to make it a rest end point and then we'll push this applicaiton to Pivotal Cloud Foundry.

###What is Spring Boot Initializr?
Spring Boot Initializr is a fast way to generate a skelton applicaiton and all the necessary dependancies for a spring boot appliciaton.   Visit https://start.spring.io/ and switch into the full version to see the types of applicaitons it can create.

**Setup
Start by making a directory and changing into it
```
mkdir springboot
cd springboot
```

**Download the starter files from start.spring.io
```
curl start.spring.io/starter.zip -o demo.zip -d dependencies=web -d javaVersion=1.7
unzip demo.zip
```

**Look around at the code


**add an examplecontrollerclass**
using vim, emax or nano add type in the code in ExampleController.java file
or you can avoid typing the code by using the following command to copy it into your environment.
```
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/master/ExampleController.java -o src/main/java/com/example/ExampleController.java
```

**Build it and run it**
```
mvn clean install
java -jar target/demo*.jar
```

**browse to localhost:8080**

**Build it and run it**
```
cf login -a api.run.pivotal.io -u jfunk@pivotal.io -o Channel -s Denver-CloudBrews
cf push bootapp -p target/demo-0.0.1-SNAPSHOT.jar --random-route
```
